# Custom NGINX Docker Image

This project demonstrates how to build a custom Docker image using the official NGINX image as a base, serve a custom `index.html` file, and push the image to Docker Hub.

## 🧾 Project Structure

. ├── Dockerfile └── index.html



### `Dockerfile` Content

```Dockerfile
FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
This Dockerfile:

Uses the latest official nginx image.

Copies local files (like index.html) into the NGINX default serving directory.

Exposes port 80.

Runs NGINX in the foreground (required for Docker containers to stay alive).

index.html Content
html
Copy

</head>
<body>
  <h1>Hello from NGINX SERVER!</h1>
  <p> THIS IS CUSTOUM dOCKER image. </p>
</body>
</html>
Note: You may want to correct the typo "CUSTOUM dOCKER" to "CUSTOM DOCKER" for a more professional appearance.

🚀 How to Build, Run, and Push
1. Build the Docker Image

docker build -t samintelli/nginx-server .
This builds the Docker image and tags it as samintelli/nginx-server.

2. Run the Docker Container


docker run -d -p 80:80 samintelli/nginx-server
This starts the container in detached mode and maps port 80 on your host to port 80 in the container.

3. Access the Application

curl http://localhost:80
Or visit http://localhost in your browser to see the custom message.

4. Push to Docker Hub

docker push samintelli/nginx-server
Make sure you're logged in to Docker Hub (docker login) and have permission to push to the samintelli namespace.

🐳 Result
You’ll see a page displaying:

Hello from NGINX SERVER!
THIS IS CUSTOUM dOCKER image.
