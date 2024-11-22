# 使用 Node.js 作為基礎映像
FROM node:14 AS build

# 設定工作目錄
WORKDIR /usr/src/app

# 複製 package.json 和 package-lock.json
COPY package*.json ./

# 安裝依賴
RUN npm install

# 複製應用程序代碼
COPY . .

# 建立 React 應用程序
RUN npm run build

# 使用 Nginx 作為伺服器
FROM nginx:alpine

# 複製建置好的應用程序到 Nginx 的預設目錄
COPY --from=build /usr/src/app/build /usr/share/nginx/html

# 暴露 Nginx 的 80 端口
EXPOSE 80

# 啟動 Nginx
CMD ["nginx", "-g", "daemon off;"]
