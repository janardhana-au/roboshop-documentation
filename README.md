# roboshop-documentation
to destroy all the resources :

for dir in $(ls -d */ | sort -r); do
  echo "Destroying: $dir"
  (cd "$dir" && terraform destroy -auto-approve)
done


To  create all the resources

for i in 00-vpc/ 10-security_group/ 20-bastion_host/ ; do cd $i; terraform apply -auto-approve ; cd ..;done