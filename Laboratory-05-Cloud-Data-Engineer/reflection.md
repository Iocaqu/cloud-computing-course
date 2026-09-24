# Mission Reflection


**1. Why is object storage better suited for storing millions of photos compared to a traditional block storage hard drive?**

Block storage works more like a hard drive attached directly to one server, so as the number of files grows you'd have to keep adding bigger or more disks and manage a file system on top of all of it, which gets messy fast once you're talking about millions of images. Object storage handles this completely differently — every photo is stored as its own object with metadata and a unique ID in a flat structure, and it's accessed over the web instead of through a traditional file path. That means it can scale to huge amounts of data without me having to manage individual drives, and it's a lot cheaper for data like photos that mostly just get stored and read, not constantly edited.

**2. How did using Docker make it easier to deploy the MinIO storage server?**

Without Docker, I would've had to manually install MinIO, set up all its dependencies, and configure it to work with my specific Ubuntu environment, which takes a lot more time and room for error. Docker packages all of that into one image, so all I had to do was run a single `docker run` command with the right flags and the server was up and running in seconds. The ports and login credentials were also just set through simple flags in that same command instead of me having to dig through config files.

**3. What is a "bucket" in the context of cloud storage?**

A bucket is basically a named container that holds your objects in object storage. It's kind of like a top-level folder, except the objects inside aren't nested in subfolders the way a normal file system works — it's flatter than that. Each bucket has its own name and its own permissions, and in this lab `client-photos` was the bucket I created to hold the uploaded images.

**4. How do you think large enterprise companies ensure their object storage data is not lost if the physical server crashes?**

I think the main way is by replicating the same data across multiple physical servers, often spread across different data centers or even different regions, so if one server goes down there are still other copies available. Companies also use things like erasure coding, where data gets split into chunks with extra redundancy built in (MinIO actually supports this in its distributed mode), along with automated failover so the system can keep working even if part of it crashes.

**5. How is your confidence in navigating the Linux command line growing?**

My confidence in the Linux command line is definitely growing. At first the terminal felt intimidating, but going through labs like this one made it a lot more manageable. Having clear commands to reference online helped me understand what each part of a command was actually doing instead of just copying and pasting blindly. I'm starting to recognize patterns in how commands are structured, which makes me feel more comfortable experimenting instead of being afraid of breaking something.
