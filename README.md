# PCA-GPU-based-vector-summation.-Explore-the-differences.
i) Using the program sumArraysOnGPU-timer.cu, set the block.x = 1023. Recompile and run it. Compare the result with the execution confi guration of block.x = 1024. Try to explain the difference and the reason.

ii) Refer to sumArraysOnGPU-timer.cu, and let block.x = 256. Make a new kernel to let each thread handle two elements. Compare the results with other execution confi gurations.
## Aim:
To explore the differences between the execution configurations of PCA-GPU-based vector summation.

## Procedure:
1. The program will start executing, and you will see the name of the device being used printed on the console.

2. The vector size is set to 2^24, which corresponds to 16,777,216 elements. This can be modified by changing the nElem variable in the code.

3. The program will allocate memory for the host arrays h_A, h_B, hostRef, and gpuRef using malloc().

4. Random values will be generated and assigned to the host arrays h_A and h_B using the initialData() function.

5. The sumArraysOnHost() function will be called to perform vector addition on the host CPU. The result will be stored in the hostRef array.

6. Memory will be allocated on the GPU for the device arrays d_A, d_B, and d_C using cudaMalloc().

7. The data from the host arrays h_A and h_B will be copied to the corresponding device arrays d_A and d_B using cudaMemcpy().

8. The kernel function sumArraysOnGPU() will be invoked on the GPU using the specified grid and block dimensions. The grid dimensions are calculated based on the number of elements and the block dimensions.

9. The GPU execution time will be measured using the seconds() function and printed on the console.

10. The device array d_C will be copied back to the host array gpuRef using cudaMemcpy().

11. The checkResult() function will be called to compare the results of the host and device arrays and check if they match.

12. Finally, the device memory and host memory will be freed using cudaFree() and free() respectively.

13. The program will terminate, and you will see the result of the comparison between the host and device arrays printed on the console.

## Output:
1- Block size = 1023
![image](https://github.com/Kavya-Bollineni22/PCA-GPU-based-vector-summation.-Explore-the-differences./assets/75235813/83308c2f-1475-45a4-b974-d9a26e32f5df)

Block size = 1024
![image](https://github.com/Kavya-Bollineni22/PCA-GPU-based-vector-summation.-Explore-the-differences./assets/75235813/0dc8e801-33d6-4eb5-b257-f3aaf83fd7d2)

2- Block size = 256. Two Threads.
![image](https://github.com/Kavya-Bollineni22/PCA-GPU-based-vector-summation.-Explore-the-differences./assets/75235813/246a40ef-ea44-4908-a248-ff5b340f27a9)

## Result:
The result of the experiment will be a comparison of the execution times and results obtained from different execution configurations. This comparison will help determine the most efficient execution configuration for PCA-GPU-based vector summation.
