# Add OpenRPC support for Filecoin Lotus

### Proposal Category: devtools-libraries, docs

### Proposer: @zcstarr

## Abstract
### What is this?

This is a proposal to add [OpenRPC](https://github.com/open-rpc/spec) support to Filecoin Lotus Client by adding the method [`rpc.discover`](https://github.com/open-rpc/spec#service-discovery-method) to the project's [JSON-RPC](https://www.jsonrpc.org/specification) API, and using go-openrpc-reflect package to support documentation of the API. This will allow, Filecoin Lotus to support generating JSON-RPC clients for Lotus in multiple languages and provide users with a modern interface for using and testing the Lotus API.

## Motivation
There is a need for proper documentation of the Lotus API and for developers to interface with the Lotus API using typesafe clients. This project will make it possible to support automated type safe client generation and documentation with a minimal footprint. So documentation tracks the implementation changes in your API automatically.

## Deliverables
Support for OpenRPC and automated client generation within Filecoin Lotus. The goal would be to use automated [tooling](https://github.com/etclabscore/go-openrpc-reflect) to generate and serve the OpenRPC documenation for the API. There is a strong belief by using this tooling we will not need to modify anything with the API in order to offer this support.
1) OpenRPC documentation served by Lotus
2) Generated Clients in Typescript to start for Lotus

## Development Roadmap
The roadmap will be broken down into three phases
exploration, go-openrpc-reflect code generation, and process documentation and client generation.
1) In the exploratory phase we will, simply try and integrate the go-openrpc-reflect documentation as is into Lotus and analyze the generated API results
2) We will test the generated code, and make improvements to go-openrpc-reflect to accurately support code generation and the Lotus API
3) We will test the generated clients to verify everything is correct end to end

20 July 2020: Proposed date to start
20 Sept 2020: Proposed date to finish

## Milestones
Milestone | Hours | Cost
--- | --- | ---
Research and experimentation with Filecoin Lotus APIs | 16 | $2,000.00
Implement POC documentation generation with existing open-rpc-reflect | 32 | $4,000.00
Testing, bug fixes, and enhancements to open-rpc-reflect to better support Lotus  | 16 | $2000.00
Generating and testing auto generated clients | 16 | $2000.00
Documenting process and making automated build releases | 16 | $2000.00
**Total** |  | 	**$12,000.00**

## Maintenance and Upgrade Plans

As this project is aiming to be integrated into the API via code. The documentation and whole project is in order that the documentation maintains itself. 

That said we are targetting using the same technology in the client that we use for Ethereum Classic [Core-Geth](https://github.com/etclabscore/core-geth), which already supports Open-RPC. 

Therefore the long term support for the reflect package and OpenRPC is growing and is assured. We will fix bugs if they arise, because we have a long term interest in its success.

In terms of documentation hosting, we will not be hosting the documents, but providing all the tooling to be able to easily spin up a hosted version or run your own whitelabeled version of any documentation tools. 

All of the tooling including but not limited to ([inspector](https://github.com/open-rpc/inspector), [docs-react](https://github.com/open-rpc/docs-react), [playground](https://github.com/open-rpc/playground)) are Apache 2.0 and built to be embeddable in a myrid of context.

We will provide guidance and help spinning any of these up for you.

# Team
 
## Team Members


- Isaac Aardis (Client Team Lead - ETCLabs)(@meowbits)
- Zachery Belford (Tooling Team Co-lead - ETCLabs - OpenRPC 
 Founder) (@belfordz)
- Zane Starr (ETCLabs , Formerly Technical Lead of
    Cellarius at Consensys)(@zcstarr)
- Shane Jonas (Tooling Team Co-Lead - ETCLabs - OpenRPC Founder )(@shanejonas)

## Team Website
https://etccore.io/


## Relevant Experience

Team has a combined years of experience of over 30 years in software development. The team consist of the founders of Open-RPC and the current maintainers of the project. Additionaly we have the creator of the open source [project](https://github.com/etclabscore/go-openrpc-reflect) to be used in developing this project(Isaac Aardis). The team supports the Ethereum Classic Blockchain on a daily basis, and has many years of experience working with systems,infrastructure, and tooling.

## Team code repositories
Many of our repositories can be found here
https://github.com/etclabscore
https://github.com/open-rpc
https://github.com/etclabscore/go-openrpc-reflect

## Additional Background 
### What is OpenRPC?

The [OpenRPC](https://github.com/open-rpc/spec) Specification defines a standard, programming language-agnostic interface description for [JSON-RPC 2.0](https://www.jsonrpc.org/specification) APIs, which allows both humans and computers to discover and understand the capabilities of a service without requiring access to source code, additional documentation, or inspection of network traffic. When properly defined via OpenRPC, a consumer can understand and interact with the remote service with a minimal amount of implementation logic, and share these logic patterns across use cases. Similar to what interface descriptions have done for lower-level programming, the OpenRPC Specification removes guesswork in calling a service.

##### Structure

[This is the structure of an OpenRPC Document](https://raw.githubusercontent.com/ethereum/EIPs/master/assets/eip-1901/OpenRPC_structure.png)

JSON-RPC APIs can support the OpenRPC specification by implementing a service discovery method that will return the [OpenRPC document](https://github.com/open-rpc/spec#openrpc-document) for the JSON-RPC API. The method MUST be named `rpc.discover`. The `rpc.` prefix is a reserved method prefix for [JSON-RPC 2.0 Specification](https://www.jsonrpc.org/specification) system extensions.

### Use Case

This is the vision for the use case of OpenRPC and how it would relate to a client implementation like Lotus:
[lotus-open-rpc diagraom](https://app.diagrams.net/?lightbox=1&target=self&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Filecoin%20Lotus%20Usecase%20Document.svg#R7VtZc9s2EP41fuhDNDxEHY%2B2nKSZSVvXcafNUwciQRINSLAgaEn99d0FQImXjjSWrTRJPLawOAh83%2B5iF4Su%2FEW2fitJkf4kIsqvPCdaX%2Fm3V57nOu4c%2FqBkYyST6cwIEski22gn%2BMD%2BoXVPK61YRMtWQyUEV6xoC0OR5zRULRmRUqzazWLB208tSEJ7gg8h4X3p7yxSqZHOAmcn%2F5GyJK2f7Dq2JiN1YysoUxKJVUPkv77yF1IIZT5l6wXlCF6Ni%2Bn3Zk%2FtdmKS5uqUDurjr%2Bp398eU%2FvZztVzkq%2FtK5K98y8Yj4ZVdsZ2t2tQQwMQL%2FKjIEkU3qco4FF34uEqZoh8KEmL9CjQAZKUiUlkiHSgDM4qwnErbJxSck6JkejDTImU8ek82olL1Y%2BrSjZ0elYqu9y7c3cIJekhFRpXcQJO6Q82AVcHxzJZXO0L9Wt%2FSBpm%2BO7GKZJUo2Y69wxk%2BWKg%2FB%2Fb56bDDQhUj%2FB60m%2BTJKQz0EY6kKB6ITKiygkKwXFH5%2BhEwLK0sZpwvBBdIVC5yfJASha3kNK77LoVSIrMFaeHaDqqhCm7gBxBdOKPgKoDVLKDs7srwg82lWoi8VBLUA8egpFQrWp5M%2BwGN7ivDMbK92Zm4Hjs9rt8h9iRU7JFCxa0IqwwWRRQT%2BZOqgXaJZKcGAgCNuXZCKYsimj8F619A1fzSqHK%2Fm%2BUzm%2BWmTelx6s%2FGvXde7i%2FcFsd79tCXI8SbfAuhSdAKTdyh0MQZhN05F%2BzT7z7wTD7QaPRhGxskOzgX1%2F3o%2F71QVQmiBWca%2F2%2FIBRrNvyR6vmcJz22Kmzalx6k%2FF%2Fd%2BP2v4pmzxhNTgeQnppwa39JFyUUD0sI%2BYKuPXoUL8bhAEFhL%2BniwpvxMl08mef1tjd8Ox4oaEnxIpqjyqcb%2Fy%2FFj%2Fa4xxzVmCfTUZTaohLuEQziy2Z2Enk3A4TPE7ByjeUJTSJ2Nythilx8V9BQ6hS8OQ5jfQImVhUIrZmkZPFNBN2gGd501HfV8yGwDrbAGd3wPrreDgJy4RLt%2F3XhqucQ%2Buh01By1Cy4iI0zJtfnIYFPcje5Xrlou8aX0LJgjZiwbjvvuYDeM3PhVc%2Fsb3jZGP8%2FiUA5nWy0snkhQHrp6T3lMCq9dlpP0d5Aci2ZyOXomPjvh%2B78iYco%2BZY5AhduI0wJn9XwoTT%2FlL%2Fb4omCf5diIzBluFf14MsZV1VS1gtuNuoFA%2ByjRhmz7pNQWYmUYtfnsCuW72EnWjaA4ZGCf1gi5AXpSIROeGvd9Ib7UQQFBPVb9u8FzpyR%2Fj%2Bokpt7CkYqZRog0vXTP2B3WH5pvSxUXO7tiPrwqZRuKOSwbr1WZqW5YCBGWg882vBRy1wxnV5N54ubZql7ogGDYTgMMeAmKhkSA9Ba6lVdba7r%2BG%2BMwFJOdGvb5qPfXoN6O%2BsPZU4mlgczRrqbCVbJ%2FgOf7QkJQtHsSQZKpR%2Ble8%2BUSKxPd%2Bs3WTfS7pDNnY%2BN9k%2FYvmlgOTXc%2B7vFn1fZ07FoPYtzakkQwEOgKM67soCH9JcK3OPkQwSbmO8tGT%2FNJLy9lEJnoagvZbGdN0vO%2B8PDu9n89F8HkzdsTczvydt7zjA21A67p8t5Awuxzc6%2F903um2%2FGLywWwz8E93iPu15HrcYvMzGuIc03%2Fe%2FGtr2eOdnoq1%2FEvFsu5ll%2F8%2Bz7GpB54KRO3A%2BNrituRPvXFgfDf93oNexPla8MpsLhPkOILDuJwL9PfEN4zSEjQq62JdH%2FQwBfpxD%2B%2Bp%2BybFU4SvZbo3u74%2BLcLudeX7gzceuO%2B2eik1HjuNPp854DmrkD9yVcMcD2jU92%2BY79F7K0JW6%2B9XC%2Ba2kISlp2eB2174WFqfophsc0s1TNbw7ihOTsN3hAVw2zvxnukLVFRnJ%2B49996XPNcMgUipl%2BLjI3ghDkvGGWJmKla4lKIoleELQOSkeWYRZubGtV9qynLIq8JUZcogjDtCghwxxJXYMLEf1y4xyr%2BUdExdfP5VPw%2BSKgV2C3WlLUilFQ88pxB54dxl%2B4SaNgxPwIyisSsMiNDWc%2FEVDNToC%2BCHn6f6AzBs1MYOighj9aOjWkprnllQ%2B6oksN8MaY8a4vnunvY5eFnrGjGi%2FyjdmsVpHq1KrkFlofSkbe2lIdgPChpyk26FZ60JkPUVsSdckK7hmrl4nQT8nadwiJlUKb4Rfo2fz3pTg6TE724xAr%2FsEdatrnEkDUngsGuWyLHR58XkTYPUB%2BEigacoiHAmZ6LruZPY1PXFWXdHJUyy2Z87H5%2FgZPYdm%2Ff93HN6XWJzpMGB31uJ2%2FrprdYk5htAN6gs7xu9nFX5HgmMNvuyrSIKLWNSWmZFP2u5wUpSUOFaMhxmtfcA0BYvuuIC4uU5wVxBoZxm%2BBkeD1wGZ54gYi6lggOYJHstH%2FB6ML0B7b9yHNkPZnTGu8hDFEOQpnLQWmrxn518l%2FbtiEsfKWM4ywuuK3DglveGFKcBCt6s0i4FkvVSGIr1UxIvk24FhkdR4uyqxjJraLi8NytXgonBgyhnMj9jnNbpE9nWjWX4kWXx0N2hb0dEYuVRSfKKNOwaTcEaXeMegeecD5BGhszjEHgUJ9RuA22BXetCp8ysPg%2BehM%2FuhSyXtPPwpsq%2FOq5ftq5hGfDyeDh1O%2FYdTRSjuvrGj6xrfe%2FJf%2Fws%3D)

## Rationale

### Why do this?
Services need to figure out how to talk to each other. If we really want to build the next generation of automation, then having up to date libraries, documented APIs, and modern tools are going to provide easy discovery, on-boarding, and enable end user and developer interaction.

Use cases for machine-readable [JSON-RPC 2.0](https://www.jsonrpc.org/specification) API definition documents include, but are not limited to:

- A common vocabulary and document will keep developers, testers, architects, and technical writers all in sync.
- Server stubs/skeletons generated in many languages
- Clients generated in many languages
- Mock Server generated in many languages
- Tests generated in many languages
- Documentation Generation

[OpenRPC](https://github.com/open-rpc/spec) documents just describe [JSON-RPC](https://www.jsonrpc.org/specification) APIs services, and are represented in JSON format. These documents may be produced and served statically OR generated dynamically from an application and returned via the [`rpc.discover`](https://github.com/open-rpc/spec#service-discovery-method) method. This gives projects and communities the opportunity to adopt tools, documentation, and clients outlined in the [etclabscore/ethereum-json-rpc-specification](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1474.md) before the [`rpc.discover`](https://github.com/open-rpc/spec#service-discovery-method) method is implemented for a particular client.

## Example Implementations
- [Signatory Open RPC](https://signatory.dev)
- [Core-Geth OpenRPC Discovery](https://github.com/core-geth/core-geth#openrpc-discovery)
- [Ethereum OpenRPC Documentation(in partnership with Ethereum Foundation)](https://github.com/etclabscore/ethereum-json-rpc-specification)

## Resources
- [EDCON 2019 talk on OpenRPC and The Future of JSON-RPC Tooling](https://www.youtube.com/watch?v=UgSPMZ9FQ4Q)
- [etclabscore/ethereum-json-rpc-specification](https://github.com/etclabscore/ethereum-json-rpc-specification)
- [open-rpc.org](https://open-rpc.org)
