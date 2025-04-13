## C3po - Data Validator, Decoder & Data Parser
[github.com/5tkgarage/c3po](https://github.com/5tkgarage/c3po)

## Braza - Web Framework
[github.com/5tkgarage/braza](https://github.com/5tkgarage/braza)

### Braza - Releases
- Multi Routers
- Middlewares
- File Watcher / HotReload
- Cors
- Sessions
- Error management
- Schema Validator
- Rendering built-in (template/html)
- Implements net/http


### Exemplos

### C3po - Exemplo Basico
```go
type User struct {
    Name string `c3po:"required"`
    Age  int    `c3po:"min=18"`
}

data := &User{Name: "Luke", Age: 17}
schema := c3po.ParseSchema(data)
res := schema.Decode(data)

if res.HasError() {
    fmt.Println(res.Errors())
}

u := res.Value().(*User)
```

### Braza - Exemplo Basico
```go
func main() {
 app := braza.NewApp(nil)
 app.GET("/hello", func(ctx *braza.Ctx){
   ctx.JSON(map[string]string{"hello":"world!"},200)
 })
 app.Listen()
}
```
