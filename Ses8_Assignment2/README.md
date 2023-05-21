#Task 
______
1. Use Drupal compose file from assignment: compose-assignment-2
2. Rename image back to official `drupal:8.2`
3. Remove `build:`
4. Add secret via `external:`
5. use environment variable `POSTGRES_PASSWORD_FILE`
6. Add secret via cli, `echo “<pw” | docker secret create psql-pw`
7. Copy compose into a new yaml file on ur Swarm node1

## Once you've got the yaml file: 
vim ses_8_ans.yml</br>
docker stack deploy -c ses_8_ans.yml drupal</br>

echo "my_secret_pass" | docker secret create psql-pw -</br>

docker stack deploy -c ses_8_ans.yml drupal</br>
docker stack ps drupal</br>
</br></br>

now go over to browser, then shilpiFire:80:80 and u can install drupal since shilpiFire is the node it's running on
