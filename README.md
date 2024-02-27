## MSI Afterburner not applying profile at start-up
1. Unlock the profiles
2. Unselect 'Apply settings at startup'
3. Select your overclock profile
4. Select the 'Apply settings at startup
5. Apply all settings with the tick
6. Lock your profile

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
