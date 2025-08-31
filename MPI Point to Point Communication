#include<mpi.h>
#include<stdio.h>
int main(int argc, char** argv){
    int rank,size;
    int number;
    MPI_Init(&argc,&argv);//Initialize MPI Environmnet
    MPI_Comm_rank(MPI_COMM_WORLD,&rank);//get current process ID
    MPI_Comm_size(MPI_COMM_WORLD,&size);//get number of processes
    if(size<2){
        if(rank==0){
            printf("this program requires atleast 2 processes");
        }
        MPI_Finalize();
        return 0;
    }
    if(rank==0){
        number=100;//Example message
        printf("Process 0 sending number %d to Process 1\n",number);
        MPI_Send(&number,1,MPI_INT,1,0,MPI_COMM_WORLD);
    }else if(rank==1){
        MPI_Recv(&number,1,MPI_INT,0,0,MPI_COMM_WORLD,MPI_STATUS_IGNORE);
            printf("Process 1 received number %d from Process 0\n",number);
    }
    MPI_Finalize(); //Cleanup the mpi environment
    return 0;
}
