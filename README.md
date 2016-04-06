Install Apache web server locally

	sudo yum install httpd24
	sudo service httpd start

In /etc/httpd/conf/httpd.conf add the following lines (for Perl):

	<Directory "/var/www/cgi-bin">
	   Options +ExecCGI
	</Directory>

	AddHandler cgi-script .cgi .pl

Then:
	sudo service httpd restart

Then put all your executable files into /var/www/cgi-bin

You might also need to change the permissions to the files:
    
    chmod 775 *.cgi
