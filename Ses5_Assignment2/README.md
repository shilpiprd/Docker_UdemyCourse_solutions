# Task: 
________

1. Jump into the bindmount-sample-1 directory. 
2. We’re gonna have a container running the background, that’s Jekyll  and wathcing those files and detecting the updates and automatically updating the web server that’s built into the container.
3. Use command: 
`docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve` 
4. Then openup local host, u should be able to see the html that’s using the default template. 
5. Then, change the file in _posts\ and refresh browser to see chagnes. (change anything) . 
6. On refreshing ur browser, ud see that it’s updated automatically. 
7. Check the docker logs to see what’s actually happening in the background.
