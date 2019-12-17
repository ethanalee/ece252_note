## Final Overall

[TOC]



### File System

1. open file and get file pointer by `fopen()`
2. get `fd` using `fileno()`
3. lock and unlock file using `flock()`
4. reposition by `fseek()`
5. close file `fclose()`

### Socket

1. fill `addrinfo` manually or using `getaddrinfo()`
2. open socket using `socket()`
3. if client
   1. call `connect()`
4. if server
   1. call `bind()`
   2. call `listen()`
   3. call `accept()` to get new socket_fd for communication
5. use `send()` or `recv()` for communication
6. call `close() ` for socket_fd

### Datagram

1. fill `addrinfo` manually or using `getaddrinfo()`
2. open socket using `socket()`
3. use `sendto()` and `recvfrom()` for communication
4. call `close() ` for socket_fd

### cURL

1. `curl_global_init ( CURL_GLOBAL_DEFAULT )`
2. `curl = curl_easy_init ()`
3. if callback need to used
   1. register callback function 
   2. associate data to the callback function
4. `res = curl_easy_perform ( curl ) ;`
5. check if `res != CURLE_OK`
6. `curl_easy_cleanup ( curl )`
7. `curl_global_cleanup ()`

### Process

1. call `fork()`
2. determine parent process or child process based on pid returned by `fork`

3. parent process need to `wait()` for child process

### AIO 

1. initialize control block 
2. fill information depends on type of trigger method
3. enqueue request
4. cancel 