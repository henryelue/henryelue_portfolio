First, I created a public repository on GitHub
Then I cloned the repository locally
I wrote my HTML code and CSS and used the 3 git commands to push to my repository
git add to track files
git commit -m "Initial commit: Added HTML and CSS files."
git push


Then I logged in to AWS, and created an EC2 instance (Amazon Linux 2023, I should have used Ubuntu, as I was not familiar with Amazon Linux 2023 commands dnf is used in place of apt)
Open an SSH client (I used Git Bash).
I located the private key file using the CD command.  Then chmod 400 your-key.pem( so only me can read the pem)
I then SSH into the EC2 using ssh -i pem-key.pem EC2_PUBLIC_IP
I used the commands below to install a web server (nginx), enable the server to run on startup and start running the server
sudo dnf install nginx git -y
sudo systemctl enable nginx
sudo systemctl start nginx

I then git clone my repo into the EC2 instance to move my code there
I then copied my index.html and style.css into the nginx web root
sudo cp index.html /var/www/html/index.html 
sudo cp style.css /var/www/html/style.css

I bought a domain name “www.henryelue.space” on Namecheap
I copied the public IP of my EC2 instance and linked it to the DNS on Namecheap

