# gitlab

GitLab is an all-in-one DevOps platform that centralizes the entire software development lifecycle in one place, offering Git repository management, CI/CD automation, security, and project planning tools for teams to code, build, test, and deploy software efficiently, acting as a comprehensive alternative to tools like GitHub by integrating DevSecOps features into a single interface.

source: [GitLab](https://gitlab.com/gitlab-org/gitlab)

## opinion

GitLab is an outstanding DevOps platform that has transformed the way I manage projects. Its comprehensive features and seamless workflow make it an essential tool for any development team. For me, it’s simply a must-have.

## Give user admin rights

1. Exec into the toolbox pod:

```bash
kubectl exec -it deployments/gitlab-toolbox -c toolbox -- bash
```

2. Open the Rails console:

```bash
gitlab-rails console
```

3. Find the user and grant admin rights:

```bash
user = User.find_by(username: 'max.muster')
user.admin = true
user.save!
```
