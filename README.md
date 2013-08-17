## Magnolia CMS on OpenShift##

1. Sign up for [OpenShift account](https://openshift.redhat.com/app/account/new). Its free and instant.

2. Install [OpenShift client tools](https://www.openshift.com/developers/rhc-client-tools-install)

3. Create DIY application
```
$ rhc app create magnoliacms diy
```
If you have access to medium gear 
```
$ rhc app create magnoliacms diy -g medium
```

4. Stop the application
```
$ rhc app stop --app magnoliacms
```

5. Delete default files
```
$ cd magnoliacms
$ git rm diy/index.html
$ git rm diy/testrubyserver.rb
```

6. Pull the source code from github
```
$ git remote add upstream -m master https://github.com/shekhargulati/magnoliacms-openshift-quickstart.git
$ git pull -s recursive -X theirs upstream master
```

7. Push the source code
```
$ git push
```

8. After git push successfully completes, the application will be running at http://magnoliacms-{domain-name}.rhcloud.com.

