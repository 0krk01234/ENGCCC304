# 👋 สวัสดี! ผม [BeerNatthawut]

## 🚀 เกี่ยวกับตัวผม
#include 
#include 
#include 

typedef struct {
    char name[50];
    char specialty[100];
    char hobbies[200];
    char current_learning[100];
} developer_info_t;

int main() {
    developer_info_t me = {
        .name = "[ชื่อของคุณ]",
        .specialty = "C Programming & Network Connections",
        .hobbies = "Gaming, Music, Reading tech books, Sports",
        .current_learning = "Advanced Socket Programming"
    };
    
    printf("Hello! I'm %s\n", me.name);
    printf("I love coding in C and building network applications\n");
    printf("Always learning something new every day!\n");
    
    return 0;
}
```

## 💻 ภาษาที่ใช้
- **หลัก:** C
- **เน้นที่:** Socket Programming, Network Connections
- **เครื่องมือ:** GCC, Make, GDB, Valgrind
- **ระบบ:** Linux, Unix

## 🎯 สิ่งที่ผมทำ
```c
// การเขียนโปรแกรมเชื่อมต่อเครือข่าย
int create_tcp_connection(const char* host, int port) {
    int sockfd = socket(AF_INET, SOCK_STREAM, 0);
    struct sockaddr_in server_addr;
    
    server_addr.sin_family = AF_INET;
    server_addr.sin_port = htons(port);
    inet_pton(AF_INET, host, &server_addr.sin_addr);
    
    if (connect(sockfd, (struct sockaddr*)&server_addr, sizeof(server_addr)) < 0) {
        perror("Connection failed");
        return -1;
    }
    
    return sockfd;
}

// Server Socket
int create_server(int port) {
    int server_fd = socket(AF_INET, SOCK_STREAM, 0);
    struct sockaddr_in address;
    
    address.sin_family = AF_INET;
    address.sin_addr.s_addr = INADDR_ANY;
    address.sin_port = htons(port);
    
    bind(server_fd, (struct sockaddr*)&address, sizeof(address));
    listen(server_fd, 5);
    
    printf("Server listening on port %d\n", port);
    return server_fd;
}
```

## 🎮 เวลาว่างทำอะไร
- **🎮 เล่นเกม** - ชอบเกมที่ใช้ network multiplayer
- **🎵 ฟังเพลง** - ฟังขณะเขียนโค้ด ช่วยให้โฟกัส
- **📚 อ่านหนังสือ** - หนังสือเทคนิคเกี่ยวกับ system programming
- **🏃‍♂️ เล่นกีฬา** - วิ่ง, ว่ายน้ำ, ฟิตเนส
- **🌱 เรียนรู้** - หาความรู้ใหม่ๆ เกี่ยวกับเทคโนโลยี
- **👥 อยู่กับเพื่อน** - ไปกินข้าว เที่ยว พูดคุยเรื่องเทค

## 🛠️ โปรเจคที่กำลังทำ
```c
// Multi-threaded Chat Server
typedef struct {
    int socket;
    char username[32];
    pthread_t thread;
} client_t;

void* handle_client(void* arg) {
    client_t* client = (client_t*)arg;
    char buffer[1024];
    
    while (1) {
        int bytes = recv(client->socket, buffer, sizeof(buffer), 0);
        if (bytes <= 0) break;
        
        // Broadcast message to all clients
        broadcast_message(client->username, buffer);
    }
    
    close(client->socket);
    pthread_exit(NULL);
}

// HTTP Server Implementation
int handle_http_request(int client_socket) {
    char buffer[2048];
    recv(client_socket, buffer, sizeof(buffer), 0);
    
    // Parse HTTP request
    char* method = strtok(buffer, " ");
    char* path = strtok(NULL, " ");
    
    // Send response
    char response[] = "HTTP/1.1 200 OK\r\nContent-Type: text/html\r\n\r\nHello World!";
    send(client_socket, response, strlen(response), 0);
    
    return 0;
}
```

## 📊 GitHub Stats
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=yourusername&show_icons=true&theme=tokyonight)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=yourusername&layout=compact&theme=tokyonight)

## 🎯 เป้าหมายการเรียนรู้
- **Advanced Network Programming** - WebSocket, HTTP/2
- **System Programming** - Kernel modules, Device drivers
- **Performance Optimization** - Memory management, Multi-threading
- **Security** - Secure socket connections, Encryption

## 🤝 ติดต่อได้ที่
- 📧 **Email:** beerjuntaya@gmail.com
- 💼 **Facebook:** Nutthawut Juntayta

## 💡 คำคมที่ชอบ
```c
// Life philosophy
while (alive) {
    learn_something_new();
    write_better_code();
    help_others();
    enjoy_life();
}
```

## 🎲 Fun Facts
- 🔧 เป็นคนที่ชอบฟังเพลงมากๆ
- 🚀 เป็น trader ค่าเงิน USD
- 📡 ไม่ชอบดูหนังเลย
- 🎮 เล่นเกมแล้วชอบคิดว่าเกมนี้ใช้ network protocol อะไร
- ☕ ต้องมีกาแฟตอนเขียนโค้ด
