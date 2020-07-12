# Matrix_Multiply_2MapperForInput
Matrix multiplication wiith two mapper used for input two files.

Input file text pattern:
    
    A index_i index_j value(index_i,index_j)
    
    eg A 0 0 5

Run steps:

  Add two file containing both matrix in the hdfs: 

    The file is space seperated.(Note: you can change the separation type to "," etc. by changing split() function regex argument in Map class). 

  Add the file into hdfs file system: 

    Make a directory using "hdfs dfs -mkdir <directory name>" eg($ hdfs dfs -mkdir /user) 

    Add the files to hadoop file system by using command "hdfs dfs -put <location of file> <directory in hdfs that you have made>" eg($ hdf dfs ~/Documents/A.txt /user/mtxM/input/) 

  Now to run the program first make a jar file by using the command "mvn clean install". (Note: A jar is already present in the  repository )

  Once the jar is build, use the following command to run jar in hadoop: 

    $ hadoop jar <location/name/of/jar> matrix_multiplication.MatrixMultiplication <hdfs input file1 location> <hdfs input file2 location> <hdfs output location> <i> <j> <k> 

    where i, j, k are the dimensions of the 2 matrix eg A(i,j) B(j,k)

  eg of command: 

    $ hadoop /target/matrix_multiplication-0.0.1-SNAPSHOT.jar matrix_multiplication.MatrixMultiplication /user/mtxM/input/A.txt /user/mtxM/input/B.txt /user/mtxM/output 10000 10000 10000
    
    
