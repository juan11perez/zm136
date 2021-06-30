  ```
  zm136:
    container_name: zm136
    image: juan11perez/zm136
    restart: unless-stopped
    hostname: UNRAID  
    # runtime: nvidia
    network_mode: "bridge"
    privileged: true
    shm_size: 16G   
    volumes:
    - /mnt/cache/appdata/cctv/zm136/config:/config:rw
    - /mnt/disks/storage/cctv/zm136/data:/var/cache/zoneminder
    environment:
    - TZ=Asia/Dubai
    - PUID=99
    - PGID=100
    - MULTI_PORT_START=0
    - MULTI_PORT_END=0
    # - NVIDIA_VISIBLE_DEVICES=<> 
    # - NVIDIA_DRIVER_CAPABILITIES=all
    ports:
    - 8088:80/tcp #http view     # - 8444:443/tcp     
    - 9000:9000/tcp

