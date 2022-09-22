# Controller Pattern
#k8s


## Psuedocode

```go
for {
  desired := getDesiredState()
  current := getCurrentState()
  makeChanges(desired, current)
}
```