# Reflection — Mission 4

Watching a Docker container start compared to a Virtual Machine really drove home why containers have taken over cloud deployment. Setting up a VM means downloading an OS image, allocating virtual CPU and memory, walking through an installer, and only then installing and configuring the application — realistically a fifteen-to-twenty-minute process. Running `docker run` on the Nginx image, by contrast, had the web server live in seconds, because there's no operating system to boot; the container just launches as an isolated process on top of the host's existing kernel.

Port mapping with `-p 8080:80` matters because containers are network-isolated from the host by default. Nginx listens on port 80 inside the container, but that port isn't exposed anywhere outside it unless you explicitly bind it to a host port. The `-p 8080:80` flag creates that bridge, so a browser or `curl` request to `localhost:8080` on the host gets routed into port 80 inside the container.

Running `docker rm` deletes the container's writable layer entirely, which means any files or data created while the container was running disappear along with it — unless that data was stored in a mounted volume outside the container. That's the tradeoff of containers being disposable by design: great for consistency, but it means persistence has to be handled deliberately.

For DevOps, containers close the gap between "works on my machine" and "works in production." Developers can package an app with everything it needs to run, and that exact package moves unchanged through testing and into production, so operations teams spend less time chasing environment mismatches and more time on scaling and reliability.

*(Wrap up with how this lab specifically moved your own GitHub portfolio forward.)*
