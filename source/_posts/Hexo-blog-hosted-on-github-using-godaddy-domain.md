---
title: Hexo blog hosted on github using godaddy domain
catalog: true
date: 2017-08-28 22:58:19
subtitle:
header-img:
tags:
- hexo
- githubPagesAndHexo
- githubHexoGodaddy
- GodaddyDomainSetupForGithub
- hexoBlog
---
If you are intending to setup a blog using hexo and host it using github pages with your custom domain being taken from godaddy, here is a step by step process on how to do it.
I faced some issues with successfully setting up my godaddy domain with github and I hope I can help somebody facing a similar issue.

1. First of all we need to install hexo. Enter this command in your terminal.

    $ sudo npm install -g hexo-cli

2. Next create a new hexo project

    $ hexo init myProject
    $ cd myProject
    $ npm install

3. Run your project to see if everything is working fine.

    $ hexo server

4. Edit the config.yml file to enter your information and to point it to your github repo.

    deploy:
      type: git
      repo: git@github.com:yourUsername.github.io.git
      branch: master

5. Make sure you use your github username while creating your github page and the branch is master when you deploy, you need that for your github.io site to work.

6. Create a new hexo post

    $ hexo new "My first post"

7. It's time to deploy!

    $ hexo clean
    $ hexo deploy

8. You can now see your blog running at yourUsername.github.io

You are done with the job if that's all you needed, but if you are using a custom domain for your blog there are a couple more things to be done.

1. Add a new file to the root of your hexo project and name it "CNAME". Inside this file type the name of the custom domain you want to use.

2. Now, for the custom domain to work you would also need to make some changes with domain provider, in this case we will go through how to do that if you domain provider is Godaddy.

3. So, sign in to your godaddy account and go to the "My Products" tab.

4. After that for the domain you want to use, click on the "Manage" option for that domain.

5. Scroll down to the bottom of the page and click the “Manage DNS” button

6. Now, when you are on the DNS management page, do the following-

    - For the Type “A” row update the IP address to: 192.30.252.153

    - For the CNAME row with Name “www” input your gh-pages website (yourUsername.github.io)

    - Now, click the “ADD” button at the bottom and make another Type “A” row with a different IP address of: 192.30.252.154

7. Go ahead and deploy.

And that's all! You are good to go.