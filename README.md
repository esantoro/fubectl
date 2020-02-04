# fubectl
Because it's fancy-kubectl!

## Prerequisites?
* [fzf](https://github.com/junegunn/fzf)
* [kubectl](https://github.com/kubernetes/kubernetes)
* [kubectl tree](https://github.com/ahmetb/kubectl-tree)
* [jq](https://stedolan.github.io/jq/)

## Installation

You can directly download the [`fubectl.source`](https://rawgit.com/kubermatic/fubectl/master/fubectl.source)
and save it in some directory.

Download:
```bash
curl -LO https://rawgit.com/kubermatic/fubectl/master/fubectl.source
```

then add to your .bashrc/.zshrc file:
```bash
[ -f <path-to>/fubectl.source ] && source <path-to>/fubectl.source
```

## What can it do?

### k - alias for kubectl

Like g for git but 133% more effective!

Examples:
 - `k get nodes`
 - `k get pods`
 - `k version --short`

Usage:
![kGif](./demo_src/k.gif)

---

### kall - All pods in all namespaces

Get all pods

Usage:
![kGif](./demo_src/kall.gif)

---

### kwall - Watch all pods in all namespaces

Watch all pods in all namespaces every 2 seconds.

Usage:
![kGif](./demo_src/kwall.gif)

---

### kdes - Describe a resource

Examples:
- `kdes pod`
- `kdes service`
- `kdes nodes`

Usage:
![kGif](./demo_src/kdes.gif)

---

### kdel - Delete a resource

Examples:
- `kdel pod`
- `kdel secret`
- `kdel pvc`

Usage:
![kGif](./demo_src/kdel.gif)

---

### klog - Print the logs for a container in a pod

Examples:
- `klog` - Print the last 10 lines
- `klog 100` - Print the last 100 lines
- `klog 250 -f` - Print the last 250 lines and follow the output, like `tail -f`
- `klog 50 -p` - Print the last 50 lines of the previous container

Usage:
![kGif](./demo_src/klog.gif)

---

### kex - Execute a command in a container

Examples:
- `kex bash` - Start a bash in a container
- `kex date` - Print the date in a container

Usage:
![kGif](./demo_src/kex.gif)

---

### kfor - Forward one or more local ports to a pod

Examples:
- `kfor 8000` - Forwards port 8000 to a pod
- `kfor 8000:80` Fowards local port 8000 to a pod's port 80

Usage:
![kGif](./demo_src/kfor.gif)

---

### ksearch - Search for string in resources

Examples:
- `// TODO`

Usage:
![kGif](./demo_src/ksearch.gif)

---

### kcl - Displays one or many contexts from the kubeconfig file
Context list

Usage:
![kGif](./demo_src/kcl.gif)
---
### kcs - Sets the current context

Usage:
![kGif](./demo_src/kcs.gif)

---

### kcns - Switch the default namespace

`kcns` - Set the current default namespace from list
`kcns kube-system` - Set kube-system as default namespace immediately

Usage:
![kGif](./demo_src/kcns.gif)
---

### kdebug - Start a debugging Pod in a Cluster

Usage:
![kGif](./demo_src/kdebug.gif)

---

### kp - Open the Kubernetes dashboard

Opens `localhost:8001/ui` in your browser and runs `kubectl proxy`

---

## Extra!
Do you wan't to have the current kubecontext in your prompt?:
```bash
export PS1="\[$(kube_ctx_name)\] $PS1"
```

for the current namespace (this is currently slow, because it calls kubectl every time):
```bash
export PS1="\[$(kube_ctx_namespace)\] $PS1"
```
