# SendMeFar
#!/bin/bash
ci/cd
echo &quot; Building Docker image...&quot;
docker build -t myapp:latest .
echo &quot; Stopping old container (if running)...&quot;
docker stop myapp || true
docker rm myapp || true
echo &quot; Running new container...&quot;
docker run -d --name myapp -p 5000:5000 myapp:latest
echo &quot; App deployed at:&quot;
echo &quot;http://$(hostname -i):5000&quot;


step:
wget -O input/image.jpg https://picsum.photos/600/400

Run Containers in Sequence (simulate Step Functions)

# Resize the image
docker run --rm -v $(pwd)/input:/data/input -v $(pwd)/output:/data/output resize-image
# Watermark the resized image
docker run --rm -v $(pwd)/input:/data/input -v $(pwd)/output:/data/output watermark-image

Now run the following Command:
python3 -m http.server 8080
