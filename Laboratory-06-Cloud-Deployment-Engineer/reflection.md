# Mission Reflection

**1. What was easier about Compose than typing Docker commands manually?**
Docker Compose was easier because one command, `docker-compose up -d`, started every container, and `docker-compose down` stopped and removed them. Instead of typing a long `docker run` command with ports, passwords and settings for each container, I wrote everything once in a file. This reduced typing mistakes and made the setup easy to repeat, version-control and share with other engineers.

**2. What error appeared when you used Tab instead of spaces?**
When I used a Tab for indentation, Docker Compose failed with a YAML parsing error because YAML does not allow tabs for indentation, and nothing was deployed. I learned that spacing in YAML is part of the structure, so one wrong indent can break the whole configuration. Using two spaces consistently fixed it.

**3. Why are environment variables useful in Docker Compose?**
Environment variables let containers receive settings such as the database name, username and password without changing the Docker image. Using the same values in both services allowed Nextcloud to connect to MariaDB. However, plaintext passwords in a Compose file are acceptable only for a proof of concept. In a real deployment they should be protected with Docker secrets or an `.env` file kept out of GitHub.

**4. What was your honest reaction when the Nextcloud page loaded?**
I felt happy and excited when the Nextcloud setup page loaded, because it proved that both containers were running and communicating correctly. I was surprised that a private cloud storage system, similar to the services companies pay for, could be running within minutes from a single file I wrote.

**5. What did you think cloud computing was in Mission 1, and what do you think now?**
In Mission 1, I thought cloud computing was simply storing files and accessing services through the internet. Now I understand that it also involves deploying and managing applications, containers and databases that work together as one system. I also learned that engineers describe this infrastructure as code so it can be repeated reliably.
