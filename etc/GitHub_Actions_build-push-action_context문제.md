# docker/build-push-action context 문제
## 문제
- docker/build-push-action 사용할때 context를 Github URL **특정폴더**로 지정하면 에러난다.
- https://github.com/jmParkGit/Sparta_docker/runs/4660352238?check_suite_focus=true
```Yaml
name: Build and push
        id: docker_build
        uses: docker/build-push-action@v2
        with:
          context: "${{ github.server_url }}/${{ github.repository }}.git#${{ github.sha }}:memo-app"
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/docker-memo:latest
```
```Shell
Run docker/build-push-action@v2
2
  with:
3
    context: https://github.com/jmParkGit/Sparta_docker.git#a20a3469c07ab9efdc874567bd86c388cf9a7ba9:memo-app
4
    push: true
5
    tags: ***/docker-memo:latest
6
    load: false
7
    no-cache: false
8
    pull: false
9
    github-token: ***
10
Docker info
11
  /usr/bin/docker version
12
  Client:
13
   Version:           20.10.11+azure-3
14
   API version:       1.41
15
   Go version:        go1.16.12
16
   Git commit:        dea9396e184290f638ea873c76db7c80efd5a1d2
17
   Built:             Wed Nov 17 23:49:46 2021
18
   OS/Arch:           linux/amd64
19
   Context:           default
20
   Experimental:      true
21
  
22
  Server:
23
   Engine:
24
    Version:          20.10.11+azure-3
25
    API version:      1.41 (minimum version 1.12)
26
    Go version:       go1.16.12
27
    Git commit:       847da184ad5048b27f5bdf9d53d070f731b43180
28
    Built:            Thu Nov 18 00:21:59 2021
29
    OS/Arch:          linux/amd64
30
    Experimental:     false
31
   containerd:
32
    Version:          1.4.12+azure-1
33
    GitCommit:        7b11cfaabd73bb80907dd23182b9347b4245eb5d
34
   runc:
35
    Version:          1.0.3
36
    GitCommit:        f46b6ba2c9314cfc8caae24a32ec5fe9ef1059fe
37
   docker-init:
38
    Version:          0.19.0
39
    GitCommit:        
40
  /usr/bin/docker info
41
  Client:
42
   Context:    default
43
   Debug Mode: false
44
   Plugins:
45
    buildx: Docker Buildx (Docker Inc., 0.7.1+azure-2)
46
    compose: Docker Compose (Docker Inc., 2.2.2+azure-1)
47
  
48
  Server:
49
   Containers: 1
50
    Running: 1
101
#1 0.125 hint: 
102
#1 0.125 hint: 	git config --global init.defaultBranch <name>
103
#1 0.125 hint: 
104
#1 0.125 hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
105
#1 0.125 hint: 'development'. The just-created branch can be renamed via this command:
106
#1 0.125 hint: 
107
#1 0.125 hint: 	git branch -m <name>
108
#1 0.126 Initialized empty Git repository in /var/lib/buildkit/runc-overlayfs/snapshots/snapshots/1/fs/
109
#1 0.161 fatal: Not a valid object name a20a3469c07ab9efdc874567bd86c388cf9a7ba9^{commit}
110
#1 1.312 fatal: could not read Username for 'https://github.com': terminal prompts disabled
111
#1 ERROR: failed to fetch remote https://github.com/jmParkGit/Sparta_docker.git: exit status 128
112
------
113
 > [internal] load git source https://github.com/jmParkGit/Sparta_docker.git#a20a3469c07ab9efdc874567bd86c388cf9a7ba9:memo-app:
114
#1 0.125 hint: 
115
#1 0.125 hint: 	git config --global init.defaultBranch <name>
116
#1 0.125 hint: 
117
#1 0.125 hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
118
#1 0.125 hint: 'development'. The just-created branch can be renamed via this command:
119
#1 0.125 hint: 
120
#1 0.125 hint: 	git branch -m <name>
121
#1 0.126 Initialized empty Git repository in /var/lib/buildkit/runc-overlayfs/snapshots/snapshots/1/fs/
122
#1 0.161 fatal: Not a valid object name a20a3469c07ab9efdc874567bd86c388cf9a7ba9^{commit}
123
#1 1.312 fatal: could not read Username for 'https://github.com': terminal prompts disabled
124
------
125
error: failed to solve: failed to read dockerfile: failed to fetch remote https://github.com/jmParkGit/Sparta_docker.git: exit status 128
126
Error: buildx failed with: error: failed to solve: failed to read dockerfile: failed to fetch remote https://github.com/jmParkGit/Sparta_docker.git: exit status 128
```

## 해결한 방법
- checkout 후, workspace/특정폴더 로 context 지정함.
- ```./memo-app``` 혹은 ```"${{  github.workspace  }}/memo-app"```
- https://github.com/jmParkGit/Sparta_docker/actions/runs/1634769223
```Yaml
name: Build and push
        id: docker_build
        uses: docker/build-push-action@v2
        with:
          context: "${{  github.workspace  }}/memo-app"
          push: true
          tags: ${{ secrets.DOCKERHUB_USERNAME }}/docker-memo:latest
```

## 기타
- github Docs: https://docs.github.com/en/actions/learn-github-actions/contexts
