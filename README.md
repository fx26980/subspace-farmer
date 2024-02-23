# Subspace farmer


Git Repository for Subspace Farmer Release Versions

More details see https://github.com/fx26980/subspace-farmer/releases

### Operating Conditions
#### 1. Ubuntu 18 or above.
#### 2. Only supports x86 CPUs.
#### 3. SSD hard drive.
#### 4. Node type must be gemini-3h.

### Running Farmer
#### 1. Choose to download from the release page.
#### 2. Running Farmer.
   `./subspace-farmer farm --reward-address <YOURADDRESS> --node-rpc-url <YOURNODE> --plotting-cpu-cores '0,1,16-17' path=/data,size=5T`
   <br/><br/>
   `./subspace-farmer farm --reward-address <YOURADDRESS> --node-rpc-url <YOURNODE> --plotting-cpu-cores '0,1,16-17 2,3,18-19' path=/data1,size=5T path=/data2,size=5T`

### General Options

 Parameter | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              
|-------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| --reward-address arg | Address for farming rewards                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --node-rpc-url arg | WebSocket RPC URL of the Subspace node (default: ws://127.0.0.1:9944)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| --plotting-cpu-cores arg  | Specify exact CPU cores to be used for plotting bypassing any custom logic farmer might use otherwise.<br/> Each path corresponds to CPU cores groups, and if there are multiple paths, they are separated by spaces.<br/>Examples: `0,1,16-17` - use cores 0, 1, 16 and 17<br/><br/>A 32-core, 64-threads CPU can be used for  processing in a 2+2 mode, such as  --plotting-cpu-cores '0,1,16,17 2,3,18,19' path /data1,size=1T /data2,size=1T , where 0,1 and 2,3 represent physical cores, and 16,17 and 18,19 represent hyper-threading. They process data1 and data2 respectively. |
| --replotting-cpu-cores arg  | If empty, it inherits --plotting-cpu-cores.<br/> Options if specified. Requires `--plotting-cpu-cores` to be specified with the same number of CPU cores groups.
| path  | One or more farm located at specified path, each with its own allocated space <br/> path=/path/to/directory,size=5T                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| -v [ --version ] | Print version                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| -h [ --help ] | Help info                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |