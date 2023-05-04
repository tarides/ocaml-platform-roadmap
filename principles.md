# Design Principles

The goal of this section is to outline the principles that will guide the
desired OCaml developer experience. Rather than focusing on specific tools or
technologies, this section aims to provide a general sense of what it will feel
like for developers to use the OCaml Platform.

The principles outlined in this section are presented as statements of desired
outcomes, rather than as achievements that have already been realized. These
principles are organized around the themes of **defaults**, **workflows**,
**evolution**, **sharing**, **openness**, **interoperability**,
**accessibility**, and **sustainability**.

## (R1: **Defaults**) Have good defaults, but be customisable

Having good defaults is important for the OCaml Platform because it allows us to
offer a smooth onboarding experience for users. By providing each tool with
sensible default configurations, we can minimise the number of choices that
users have to make and allow them to quickly start writing and experimenting
with OCaml code. Consistency between the default configurations ensures no
surprise when installing a new platform tool.

At the same time, we recognise that advanced users may want more control over
their experience, so we strive to make our tools flexible and customisable. This
allows users to tailor the OCaml Platform to their specific needs and workflows
while benefiting from our default configurations. The defaults can always be
taken as a base to extend, resulting in a smooth customization experience.  

Having good defaults should span over multiple workflows, even advanced ones,
allowing users to quickly get started with OCaml development and be productive
without needing to do any configuration or installation themselves. This
includes providing tools that support the entire development workflow, from
writing and formatting code to building and testing, documentation and
publishing.

By offering a feature-complete set of tools with sensible and consistent
defaults, the OCaml Platform aims to provide a seamless and efficient experience
for all users, regardless of their level of expertise. At the same time, the
OCaml Platform also allows for customisation and configuration to support the
needs and tastes of advanced and power users. By offering good defaults and
allowing for customisation, we can provide a developer experience that is both
accessible and powerful.

## (R2: **Workflows**) Workflows are easy to understand and can scale

The development model for the OCaml Platform should be simple and easy for
developers to understand and reason about. Complexity should be removed rather
than covered up with convenient tools. While supporting legacy users is
important, we should deprecate and eventually abandon workflows that detract
from the simplicity of the core.

Workflows should scale seamlessly as projects grow and evolve. This doesn't mean
that they won't change as projects become more complex, but developers should
not need to shift tools or approaches completely as their projects grow.

Reproducibility is a key aspect of the supported OCaml Platform workflows, that
can be achieved elegantly by avoiding the notion of "state" in a project. This
idea of "configuration over commands" suggests replacing existing tools and
commands with a single configuration-based approach that can effectively manage
and update the project environment. While package managers and lock files can
help, they also lead to many files and complexity in the project directory. It
would be beneficial to have a simpler way to explicitly control and manage
package versions, potentially through a configuration file. While this is a
radical approach, it offers an interesting perspective on streamlining and
simplifying the development process. We want the OCaml Platform to be able to
experiment with these ideas.

The tools should be predictable in their behaviour. This means that developers
should be able to understand how the tools will behave in different situations,
without having to spend time experimenting or debugging. The tools should be
consistent across different projects and environments. Developers should be able
to use the same tools, with the same configuration, for different projects and
in different environments. This will help developers to focus on writing code,
rather than having to constantly adjust their tools and configurations.

A simple model also makes it easier to explain the platform to users. The tools
should be designed to make it easy for people encountering the platform for the
first time. In particular, the tools should provide helpful feedback when users
make common mistakes, such as misspelling a subcommand or trying to start a
build before creating the necessary files. The tools should prioritise
helpfulness over concision and provide suggestions for potential solutions when
possible.

## (R3: **Evolution**) Tools evolve without breaking existing projects

We recognize the importance of evolution to keep up with the changing needs of
developers. We strive to ensure that our tools can evolve without breaking
existing projects, and we prioritize backward compatibility in our design
decisions. This allows developers to use the latest features and improvements
without worrying about compatibility issues.

Additionally, we believe that tools should be independently composable, enabling
developers to easily incorporate them into their existing projects. This ensures
flexibility for users, allowing them to choose the tools that work best for them
while still benefiting from the improvements and advancements made to the OCaml
Platform.

To guarantee the long-term sustainability of our tools, each project should have
a dedicated team of maintainers responsible for their maintenance and
improvements. These projects should prioritize addressing real developer pain
points, and the OCaml Platform will only adopt tools that have demonstrated
traction and adoption within the community. This commitment ensures that our
tools remain useful, relevant, and widely used by the OCaml community.

## (R4: **Sharing**) Sharing code and docs is straightforward and secure

The OCaml Platform should make it easy for developers to share their code and
documentation with others. This means providing tools and workflows that help
developers publish their projects in a high-quality and secure manner. By
catching common errors during the development process and providing guidance on
best practices for publishing, the OCaml Platform can help ensure that projects
are ready for publication without any additional hurdles.

In addition to making it easy to publish projects, the OCaml Platform should use
the best practices in supply chain management. One example of a best practice in
this regard is the use of software bill of materials (SBOM) to accurately track
the dependencies of a project and ensure that they are secure and up-to-date.
This can help prevent the inclusion of vulnerable or outdated dependencies, and
can also facilitate collaboration and reuse of code by making it easier to
understand the dependencies of a project. Other best practices in supply chain
security include the use of secure code signing to verify the authenticity of
code, as well as the use of static analysis tools to identify and address
potential vulnerabilities before they are distributed.

## (R5: **Openness**): OSS, community and composition with non-OCaml ecosystems

One of the key design principles of the OCaml Platform is openness. This means
that the Platform is open to contributions and collaboration from the wider
OCaml community and that the tools and libraries included in the Platform are
open-source and freely available to use and modify.

Having openness as a design principle is important for several reasons. First,
it allows the OCaml Platform to benefit from the collective expertise and
knowledge of the wider OCaml community, which can lead to more robust and
feature-rich tools and libraries. Second, it enables composition and
interoperability with other open-source ecosystems, such as Rust and Wasm, which
can enhance the functionality and utility of the OCaml Platform. Third, it
promotes collaboration and sharing within the OCaml community, which can foster
a thriving ecosystem of open-source projects and contribute to the long-term
sustainability of the OCaml language and its ecosystem.

## (R6: **Interoperability**): Tools have interoperability but are also independent

The OCaml Platform accommodates both new and advanced users of OCaml. For new
users, the Platform should offer a unified experience that provides the simplest
solution to work with OCaml. This allows them to get started quickly and easily.

The unified experience, both from the editor and command line, is the
recommended way to use the Platform, for both new and advanced users. However,
advanced users should have the flexibility to configure the tools however they
see fit and stay in control of their workflows. This can be achieved by
providing standalone and independent tools that can be integrated with each
other.

Moreover, industrial users can adapt the tools of the OCaml Platform to their
specific environment. They can use and configure each tool independently to meet
their specific needs, without having to compromise on their existing workflows.
This flexibility and interoperability are key to the success of the OCaml
Platform and allow it to cater to a wide range of users, from new beginners to
experienced professionals.

Additionally, the tools are not overly dependent on each other, allowing users
the flexibility to fork or modify individual tools as needed. This again allows
industrial users to adapt the tools to their specific environment and
requirements.

## (R7: **Accessibility**): Tools are accessible to as many people as possible

The tools strive to be accessible to a wide range of users, regardless of
ability or technical background, to make OCaml programming and development more
inclusive and accessible to all. This includes but is not limited to, ensuring
compatibility with assistive technologies, clear and concise documentation, and
intuitive user interfaces. The OCaml Platform recognizes that accessibility is
an ongoing effort and is committed to continuously improving and making its
tools as accessible as possible.

## (R8: **Sustainability**): Promote Sustainable Practices and Resource Efficiency

The tools and processes of the OCaml Platform aim to minimize their
environmental impact, encouraging responsible resource usage and reducing waste
where possible. This includes considering the energy consumption and carbon
footprint of the platform's infrastructure and operations, as well as minimizing
the waste generated during development and deployment processes. The platform is
committed to promoting sustainable practices and reducing its environmental
impact over time.

The tools also strive to minimize their impact on the environment through
efficient design and performance, reducing the amount of computing resources
necessary to run the tools, thus contributing to a lower carbon footprint. The
OCaml Platform should be compatible with older hardware and systems with limited
resources, preventing the need for users to purchase new hardware and reducing
electronic waste.

Additionally, the OCaml Platform should provide tools and resources to help
developers assess and optimize the energy consumption of their applications. By
offering guidance and tools to measure energy usage, developers can make
informed decisions about their applications' efficiency, ultimately contributing
to more sustainable and environmentally-friendly software development practices.
