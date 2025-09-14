#include<mpi.h>
#include<stdio.h>
int main(int argc, char** argv){
    int rank,size;
    int number;
    int msg_send=100,msg_recv;
    MPI_Init(&argc,&argv);
    MPI_Comm_rank(MPI_COMM_WORLD,&rank);
    MPI_Comm_size(MPI_COMM_WORLD,&size);
    if(rank==0){
        printf("Enter number to broadcast:");
        fflush(stdout);
        scanf("%d",&number);
    }
    MPI_Bcast(&number,1,MPI_INT,0,MPI_COMM_WORLD);
    printf("Process %d received number:%d\n",rank,number);
    MPI_Finalize();
    return 0;
}
