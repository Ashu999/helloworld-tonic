# Example [tonic-reflection](https://crates.io/crates/tonic-reflection) Crate usage

tonic-reflection working with a simple [base example provided by tonic](https://github.com/hyperium/tonic/blob/master/examples/helloworld-tutorial.md).

After cloning, Try running some of the following commands:

```shell
Run server:
`cargo run --bin helloworld-server`

Run client: 
`grpcurl -plaintext -import-path ./proto -proto helloworld.proto -d '{"name": "Tonic"}' '[::1]:50051' helloworld.Greeter/SayHello`

(grpcurl here is acting as a client, notice we are providing the path to proto file: `-import-path ./proto -proto helloworld.proto`). This is just testing if our example works fine without tonic-reflection usage.
```

Now let's try using tonic-reflection:

```rust
we have already added reflection_service in our server.rs file
```

```shell
Run client (to use tonic-relection, not providing proto file path to client): 
`grpcurl -plaintext -d '{"name": "Tonic"}' '[::1]:50051' helloworld.Greeter/SayHello`

```

Another way of testing tonic-reflection:

```shell
run below cmd:
`grpcurl -plaintext [::1]:50051 list``

This command should output something like:
grpc.reflection.v1alpha.ServerReflection
helloworld.Greeter
```
