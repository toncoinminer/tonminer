# TonMiner
##### TONCoin GPU POW miner wrapper

## Overview
TonMiner is a cryptocurrency mining software (wrapper for https://github.com/tontechio/pow-miner-gpu/) .
Supporting multiple GPU mining on OpenCL or CUDA

Developer fee default is 2% (can be changed)

## Download
https://github.com/toncoinminer/tonminer/releases

## Usage

Full list of command line options:
```
  -L      Show GPU list and exit
  -api    Serve HTTP API [[host]:port]
  -b      Boost. (Comma separated GPU idx list) (default "64")
  -c      Config filepath. (Can use URL)
  -dev    DevFee percentage (default 2)
  -g      Giver addresses. (Comma separated)
  -gl     Giver list filepath. (Can use URL)
  -gr     Use random givers
  -i      Enabled GPUs. (Comma separated GPU idx list)
  -l      Log filepath
  -ocl    Use OpenCL for NVIDIA GPUs
  -w      Your wallet address
  -wd     On/Off thread watchdog (default 1)
```

### Examples
* **Simple**</br>
```
tonminer -w EQAXd2nGZv7-3GD3ryYJbHP4L2NtVnEDES24jbnYF4m4vYlI -g kf8SYc83pm5JkGt0p3TQRkuiM58O9Cr3waUtR9OoFq716lN-
```

* **Multiple givers**</br>
```
tonminer -w EQAXd2nGZv7-3GD3ryYJbHP4L2NtVnEDES24jbnYF4m4vYlI -g kf8SYc83pm5JkGt0p3TQRkuiM58O9Cr3waUtR9OoFq716lN-,kf8gf1PQy4u2kURl-Gz4LbS29eaN4sVdrVQkPO-JL80VhOe6,kf9iWhwk9GwAXjtwKG-vN7rmXT3hLIT23RBY6KhVaynRrIK7
```

* **Output to log file**</br>
```
tonminer -w EQAXd2nGZv7-3GD3ryYJbHP4L2NtVnEDES24jbnYF4m4vYlI -g kf8SYc83pm5JkGt0p3TQRkuiM58O9Cr3waUtR9OoFq716lN- -l tonminer.log 
```

* **Enable HTTP API on port 8080**</br>
```
tonminer -w EQAXd2nGZv7-3GD3ryYJbHP4L2NtVnEDES24jbnYF4m4vYlI -g kf8SYc83pm5JkGt0p3TQRkuiM58O9Cr3waUtR9OoFq716lN- -api ":8080" 
```

* **Use remote givers list**</br>
```
tonminer -w EQAXd2nGZv7-3GD3ryYJbHP4L2NtVnEDES24jbnYF4m4vYlI -gl https://raw.githubusercontent.com/toncoinminer/tonminer/main/givers.txt
```

* **Random giver from remote list**</br>
```
tonminer -w EQAXd2nGZv7-3GD3ryYJbHP4L2NtVnEDES24jbnYF4m4vYlI -gr -gl https://raw.githubusercontent.com/toncoinminer/tonminer/main/givers.txt
```

### API Example
```
[
  {
    "id": 0,
    "bus": 12,
    "name": "gfx1012",
    "total_hashes": 1677721600,
    "hashrate": 324156000,
    "avg_hashrate": 223284000
  },
  {
    "id": 1,
    "bus": 7,
    "name": "gfx1032",
    "total_hashes": 16475226112,
    "hashrate": 465045000,
    "avg_hashrate": 434186000
  },
  {
    "id": 2,
    "bus": 1,
    "name": "NVIDIA GeForce RTX 3080 Ti",
    "total_hashes": 39090913280,
    "hashrate": 1300379000,
    "avg_hashrate": 1260206000
  },
  {
    "id": 3,
    "bus": 3,
    "name": "NVIDIA GeForce RTX 3060",
    "total_hashes": 2583691264,
    "hashrate": 507634000,
    "avg_hashrate": 507618000
  }
]
```

