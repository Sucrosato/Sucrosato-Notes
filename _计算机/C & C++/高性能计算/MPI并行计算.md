```c
    MPI_Status status;
    MPI_Init(&argc, &argv);
    MPI_Comm_rank(MPI_COMM_WORLD, &myid);
    MPI_Comm_size(MPI_COMM_WORLD, &numprocs);
    MPI_Get_processor_name(processor_name, &namelen);
    MPI_Send(&myid, 1, MPI_INT, des, 1, MPI_COMM_WORLD);
    MPI_Recv(&mailbox, 1, MPI_INT, rec, 1, MPI_COMM_WORLD, &status);
    MPI_Finalize();
```
规约操作（具体操作查阅手册）
```c
MPI_Reduce(&mypi, &pi, 1, MPI_DOUBLE, MPI_SUM, 0, MPI_COMM_WORLD);
```
一种循环思路（等差数列）：`for(int i=1; i<=n; i+=numprocs)`

### 对等模式

阻塞通信/非阻塞通信：开始发消息后是否继续下一步；阻塞通信可能引起死锁

捆绑发送接收：防止死锁
```fortran
do i=1,steps 
! 从左向右传递数据 
    call MPI_SENDRECV(A(1,mysize+1),totalsize,MPI_REAL,myid+1,10,A(1,1),totalsize,MPI_REAL,MYID-1,10,MPI_COMM_WORLD,status,ierr) 
! 从右向左传递数据 
    call MPI_SENDRECV(A(1,2),totalsize,MPI_REAL,myid-1,10,A(1,mysize+2),totalsize,MPI_REAL,myid+1,10,MPI_COMM_WORLD,status,ierr) 
end do 
```
```cpp
MPI_Sendrecv(
            &A[0][mysize], // onst void *sendbuf; 最右侧数据, 要发送给下一个 proc
            totalsize,     // int sendcount; 数据长度
            MPI_DOUBLE,    // MPI_Datatype  sendtype; 数据类型
            right,         // int dest
            tag1,          // int sendtag,
            //---------------------------------------
            &A[0][0],       // void *recvbuf; 接收数据位置
            totalsize,      // int recvcount; 接收长度
            MPI_DOUBLE,     // MPI_Datatype  recvtype; 数据类型
            left,           // int source; 接收源
            tag1,           // int recvtag; 接收 tag
            MPI_COMM_WORLD, // MPI_Comm comm; 通信域
            &status         // MPI_Status *status; 发送或接收状态;
```
虚拟进程：MPI_PROC_NULL，处理边界
```fortran
if(myid > 0) then 
    left=myid-1 
else 
    left=MPI_PROC_NULL 
end if 
if(myid < 3) then 
    right=myid+1 
else 
    right=MPI_PROC_NULL 
end if 
```
