# node_private_git
Container which runs `npm install` followed by `npm start` and accepts ssh keys case of private repos.

# SECURITY NOTICE
>DO NOT PUSH TO DOCKERHUB!

The finished container will include a layer which will have your private and public git keys. Someone might (read: will) reverse engineer the layers to get the keys!

## fixing this issue
Use a volume bind to overwrite the /root/.ssh/ folder instead of adding it (remove line 27 through 31).

## Rationale
If I know it isn't safe and provide a solution why am I still doing things the *"wrong"* way?

Well... I can build a private image which others can use without too much knowledge of docker and ssh. <sub>(*kuch* lots of Windows users *kuch*)</sub> 


