# 使用 Go 官方映像
FROM golang:1.19-alpine

# 設定工作目錄
WORKDIR /app

# 複製 Go 源碼
COPY . .

# 編譯 Go 程序
RUN go build -o main .

# 暴露應用程序埠（與你的 API 埠一致）
EXPOSE 8080

# 啟動應用程序
CMD ["/app/main"]
