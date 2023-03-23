- Feature Name: Protobuf Definition Files
- Start Date: 2023-03-22
- MCIP PR: [mobilecoinfoundation/mcips#0064](https://github.com/mobilecoinfoundation/mcips/pull/0064)
- Tracking Issue: [mobilecoinfoundation/mobilecoin/3071](https://github.com/mobilecoinfoundation/mobilecoin/issues/3071)

# Summary
[summary]: #summary

A more ergonomic way for clients to use the 
[Protobuf](https://protobuf.dev/) definition files used for communicating with
consensus and fog services.

# Motivation
[motivation]: #motivation

Protobuf definition files are often used to generate code for communicating with
services. The Protobuf files define the binary data representation and the
generated code provides a way to convert between common code interface and the
binary data representation.

The current Protobuf definitions used for communicating with fog and
consensus are defined in the main 
[MobileCoin Foundation repository](https://github.com/mobilecoinfoundation/mobilecoin). 

Most clients end up submoduling the MobileCoin Foundation repository in order to
generate code at build time.  The MobileCoin Foundation repository is fairly
large and submoduling it to gain access to a few files is not very ergonomic.

There are better ways to make the Protobuf files available for clients to use.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

Protobuf definition files are made available in the following ways:

1. [Buf Schema Registry](#buf-schema-registry)
2. [Rust crates](#rust-crates)
3. [The Protobuf git repo](#the-protobuf-git-repo)

## Buf Schema Registry

The [Buf Schema Registry](https://buf.build/explore/) is an online hosting
platform of of Protobuf defintions. It provides documentation hosting and a
command line tool that can be used to generated code and detect breaking changes
in Protobuf definitions.

The MobileCoin Founation Protobuf files are available at
<https://buf.build/mobilecoinfoundation>.

For clients using a language supported by the Buf Schema Registry, it is the
suggested way to use the MobileCoin Foundation's Protobufs 

## Rust Crates

The MobileCoin Foundation Protobuf defintions are available via
[Rust](https://www.rust-lang.org/) crates.  These crates can be found on
<https://crates.io> by searching for
[mc-protobuf-](https://crates.io/search?q=mc-protobuf-).

Building using the crates requires the client to have
[protoc](https://grpc.io/docs/protoc-installation/), the Protocol Buffer
Compiler, installed.

## The Protobuf Git Repo

Clients can directly access the Protobuf definitions via the git repo,
<https://github.com/mobilecoinfoundation/protobufs>. 

The other two methods should be prefered over direct access to the git repo, but
there are times where it is necessary.

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation



> This is the technical portion of the MCIP. Explain the design in sufficient detail that:
>
> - Its interaction with other features is clear.
> - It is reasonably clear how the feature would be implemented.
> - Corner cases are dissected by example.
>
> The section should return to the examples given in the previous section, and explain more fully how the detailed proposal makes those examples work.

# Drawbacks
[drawbacks]: #drawbacks

> Why should we *not* do this?

# Rationale and alternatives
[rationale-and-alternatives]: #rationale-and-alternatives

> - Why is this design the best in the space of possible designs?
> - What other designs have been considered and what is the rationale for not choosing them?
> - What is the impact of not doing this?

# Prior art
[prior-art]: #prior-art

> Discuss prior art, both the good and the bad, in relation to this proposal.
> A few examples of what this can include are:
>
> - For consensus and fog proposals: Does this feature exist in other systems, and what experience have their community had?
> - For community proposals: Is this done by some other community and what were their experiences with it?
> - For other teams: What lessons can we learn from what other communities have done here?
> - Papers: Are there any published papers or great posts that discuss this? If you have some relevant papers to refer to, this can serve as a more detailed theoretical background.
>
> This section is intended to encourage you as an author to think about the lessons from other systems, provide readers of your MCIP with a fuller picture.
> If there is no prior art, that is fine - your ideas are interesting to us whether they are brand new or if it is an adaptation from other systems.
>
> Note that while precedent set by other systems is some motivation, it does not on its own motivate an MCIP.
> Please also take into consideration that MobileCoin sometimes intentionally diverges from common cryptocurrency features.

# Unresolved questions
[unresolved-questions]: #unresolved-questions

> - What parts of the design do you expect to resolve through the MCIP process before this gets merged?
> - What parts of the design do you expect to resolve through the implementation of this feature before stabilization?
> - What related issues do you consider out of scope for this MCIP that could be addressed in the future independently of the solution that comes out of this MCIP?

# Future possibilities
[future-possibilities]: #future-possibilities

> Think about what the natural extension and evolution of your proposal would
> be and how it would affect the project as a whole in a holistic way. Try to
> use this section as a tool to more fully consider all possible interactions
> with aspects of the project in your proposal. Also consider how this all
> fits into the roadmap for the project and of the relevant team.
>
> This is also a good place to "dump ideas", if they are out of scope for the
> MCIP you are writing but otherwise related.
>
> If you have tried and cannot think of any future possibilities,
> you may simply state that you cannot think of anything.
>
> Note that having something written down in the future-possibilities section
> is not a reason to accept the current or a future MCIP; such notes should be
> in the section on motivation or rationale in this or subsequent MCIPs.
> The section merely provides additional information.

