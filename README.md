# Ghost Docker

### Deployment
We are using [Now][now] for deployment. Before you begin, you will need to install the [`now-cli`][now-cli] on your machine. 

* Clone this repo.
* To deploy, run the following in the project directory:
    `now -e url=https://domain-name.com`
* This will give us a now deployment url that will look something like this:
    `https://ghostdocker-xyzabc.now.sh`
* Use this url in the next step. In order to create an alias with a custom domain on Now, follow the steps [here][domain].
`now alias <now deployment url> domain-name.com`
* Lastly, we want to scale our deployment. If we don't scale our deployment, it'll freeze after an hour and it will take a while to spin up again. Run the following: `now scale domain-name.com all 1 10`. This tells `now` to scale our deployment in all regions with a minimum of 1 instance and a maximum of 10.

Visit `domain-name.com` to see your newly created blog. To begin with Ghost, visit `domain-name.com/ghost` and create an account. As we used our custom domain name in our first Now command, our Ghost admin should work properly.

[now]: <https://zeit.co/now>
[now-cli]: <https://zeit.co/now#whats-now>
[domain]: <https://zeit.co/docs/features/aliases>
