## MSI Afterburner not applying profile at start-up
1. Unlock the profiles
2. Unselect 'Apply settings at startup'
3. Select your overclock profile
4. Select the 'Apply settings at startup
5. Apply all settings with the tick
6. Lock your profile

## Why is my GPU increasing/decreasing my core clock?
My understanding is that this is due to GPU Boost 3.0. When a GPU's temp increases or decreases, GPU Boost 3.0 was adding or subtracting 15 Mhz to the core clock speed.
For example, after booting my PC, I would notice that the applied core clock would be 1860 instead of 1875 or it would jump to 1890 then back down to 1875.
This lead me to using the Nvidia System Management Interface to limit the clock speeds of my GPU.  
https://developer.nvidia.com/nvidia-system-management-interface

## Locking GPU Clocks to specific Speed
This is accomplished by running the below command.  
Please note that it is not clear if this is officially supported on consumer Nvidia GPUs.
```
nvidia-smi -lgc 210,1920
```
-lgc is shorthand for --lock-gpu-clocks. Per the documentation this allows you to limit how low the clock speed (210) will drop and how high (1920) the clock can go.
To undo this command, run
```
nvidia-smi -rgc
```
-rgc is shorthand for --remove-gpu-clocks
