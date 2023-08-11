## Using

- Find: ````using Moq;````
- Replace: ````using NSubstitute;````

## Instance
- Find: ````new Mock<(.+?)>\((.*?)\)````
- Replace: ````Substitute.For<$1>($2)````

## Instance
- Find: ````\bMock<(.+?)>````
- Replace: ````$1````

## Setup
- Find: ````(?<!\.)\b(\w+)(\s\n\s*)?\.Setup(Get)?\((\w+) => \4(\.?.+?)\)(?=\.R|\s\n)````
- Replace: ````$1$5````
- Find: ````\.Get<(.+?)>\(\)\.Setup\((\w+) => \2(\.?.+?)\)(?=\.R|\s\n)````
- Replace: ````.Get<$1>()$3````
- Find: ````\.Get<(.+?)>\(\)\.SetupSequence?\((\w+) => \3(\.?.+?)\)(?=\.R|\s\n)````
- Replace: ````.Get<$1>()$3````
- Find: ````(?<!\.)\b(\w+)(\s\n\s*)?\.SetupSequence?\((\w+) => \3(\.?.+?)\)(?=\.R|\s\n)````
- Replace: ````$1$4````
- Find: ````\.Get<(.+?)>\(\)\.SetupSequence?\((\w+) => \2(\.?.+?)(\)(?!\)))````
- Replace: ````.Get<$1>()$3````

## Verify
- Find: ````(?<!\.)\b(\w+)\.Verify\((\w+) => \2(.+?), Times\.(Once(\(\))?|Exactly\((?<times>\d+)\))\)````
- Replace: ````$1.Received(${times})$3````
- Find: ````(?<!\.)\b(\w+)\.Verify\((\w+) => \2(.+?), Times\.Never\)````
- Replace: ````$1.DidNotReceive()$3````

## Throw

- Find: ````(?<!\.)\b(\w+)(\s\n\s*)?\.Setup\(((\w+) => \4(\..?.+?)\))\)\s*\n*\.Throws````
- Replace: ````$1.When($3).Throw````

## Arg
- Find: ````It.IsAny````
- Replace: ````Arg.Any````
- Find: ````It.Is````
- Replace: ````Arg.Is````

## MockingKernel

- Find: ````MoqMockingKernel````
- Replace: ````NSubstituteMockingKernel````

## MockingKernel using

- Find: ````using Ninject.MockingKernel.Moq;````
- Replace: ````using Ninject.MockingKernel.NSubstitute;````

## MockingKernel GetMock
- Find: ````\.GetMock<(.+?)>\(\)````
- Replace: ````.Get<(.+?)>()````
