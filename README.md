# go_podwiz
Go package for [Podwizzard_GO](https://github.com/Wodlfvllf/Podwizzard_GO) 

## Usage
You must run client before connecting to it!

**Make sure that the shell you ran podwiz_client into is pointing to the same docker-daemon as that of k8s**

```
import "github.com/Wodlfvllf/Podwizzard_GO"

func main() {
	c := Podwizzard_GO.Connect()
	creds := c.Start(name, machineName, path, imgName, timeToKill, scheduleName)
	list := c.List(scheduleName) // scheduleName doesn't affect for now, you can pass empty string
}
```
`name` must be same as the username in Dockerfile. (see how [Dockerfile](https://github.com/Wodlfvllf/PodWIzard/blob/main/chall-1/Dockerfile) should look like)

`machineName` is the name you want to give your shell.

`path` is path of a directory with Dockerfile and a pod.yaml file (see [chall-1](https://github.com/Wodlfvllf/PodWIzard/tree/main/chall-1))

`imgName` name of the image to be used for shell (If image is not found, image is built using the Dockerfile in `path`)

`timeToKill` is the amount of time (secs) after which you want to delete the shell

`scheduleName` is the name you want to assign the scheduler (development for unique schedule name is in progress, for now you can use same schedule names)
