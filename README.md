# Singleton
singleton is a small library which allows you to create single instance in an application
```shell
go get github.com/go-pkg-utils/singleton
```
For example:
------------
```go
func main() {
	r1 := singleton.GetInstance(func() *Redis {
		return &Redis{Host: "127.0.0.1"}
	})

	r2 := singleton.GetInstance[Redis]()

	fmt.Println("r1==r2:", r1 == r2)

	r1.Host = "localhost"
	fmt.Println("r1==r2:", r1 == r2)

	r2.Host = "127.0.0.1"
	fmt.Println("r1==r2:", r1 == r2)
}

type Redis struct {
	Host string
}
```
