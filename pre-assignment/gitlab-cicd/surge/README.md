# Surge.sh
Surge is a cloud platform for hosting static websites which is extreamly easy to use.

## Installing surge.sh
To use surge you first need to node and npm by:
Mac: https://formulae.brew.sh/formula/node#default
Windows: https://medium.com/devops-with-valentine/how-to-install-node-js-and-npm-on-windows-10-windows-11-139442f90f12

You can then install surge with the command `sudo npm install --global surge`.

## Setting up surge.sh
Now that surge is installed you can set it up by using the command `sudo surge` and then providing your email, a password, and the path to the public folder that we created with gatsby earlier, when prompted (you can also provide a domain name if you want to, otherwise you can use the one it provides).

You can now go to that domain and you will see your website.

## Removing your website
To un-host your website simply use the command `surge teardown your-domain-name.surge.sh`

## Security with surge
When we use surge in our CI/CD pipeline script we dont want to enter our credentials so we can save them on Gitlab.
To do this:
1) In the terminal we just used to set up serge use the command `surge token` and copy the output.
2) In gitlab inside your project hover over "settings" and click on "CI/CD".
3) Find the "variables" section and click "expand".
4) Click "Add variable", make sure only "Protect variable" and "Expand variable reference" are ticked, enter "SURGE_LOGIN" as the "key" and the email you provided surge earlier as the "value".
5) Click "Add variable".
6) Click "Add variable" again, this time make sure only "Mask variable" and "Expand variable reference" are ticked, enter "SURGE_TOKEN" as the "key" and paste the token we got earlier as the "value".
7) Click "Add variable".
8) Now gitlab will use these credentials for surge automatically so you dont need to put them in your script.