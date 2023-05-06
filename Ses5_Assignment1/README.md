# Task: 
_______

1. Create a `postgres` container with named volume psql-data using version `9.6.1`  
2. Use Docker Hub to learn `VOLUME` path and versions needed to run it. ( you can name your volume whatever u want on the left side of colon , and right side is the path where the actual databases are gonna be in the container )  
3. check logs, stop container. (after a point , the logs will stop and the container will just run) . 
4. If done correctly, docker volume ls , see the volume listed there with the name u gave it, and u should be able to stop that container 
5. Then, create a new contianer, with a new version, just specify the different version. Also make sure that you specify the same volume since they both need to be using same data. Also make sure the 1st container is stopped since  u cant access the same data at the same time.
6. Now check the logs again for the new container, you should see there’s only a couple lines of startup logs coz it doesn’t have to do all work of initial startup.
</br></br>
In my solution code, i’ve used bind mounts, when I could have simply done -v my_db instaed of -v $(pwd)/my_db. 
