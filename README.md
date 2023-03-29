# ExecBlock - Markdown Code Block Runner

The ExecBlock is a command-line utility that allows you to
extract and execute code blocks from Markdown files.

> For hopefully obvious reasons, do not run arbitrary markdown files through this

## Usage

You may need to install the cli dependencies: `pip install rich typer`

ExecBlock supports the following command-line options:

```
Usage: execblock.py [OPTIONS] FILE_PATH

Options:
  --help  Show this message and exit.
```

To execute code blocks from a Markdown file, run the following command:

```
python execblock.py <file_path>
```

![shot silly-moon](https://user-images.githubusercontent.com/10828202/228302370-b580c410-08b2-45f9-8892-373dd95c495b.png)


This will display a list of code blocks found in the Markdown file,
along with their associated language and a truncated snippet of the
code. You can then select a code block to execute by entering its
corresponding number.

![shot cool-dog](https://user-images.githubusercontent.com/10828202/228302363-8aa0497e-fe56-484b-890f-0ed01e123775.png)

## Supported Languages

The Code Block Runner supports the following programming languages:

-   Python
-   Bash

## Example Blocks

The following code blocks can be executed, using `./execblock.py README.md`:

```python
print("Hello, World!")
```

```python
# Library Example
import numpy as np

x = np.array([1, 2, 3])
print(x)

# Plot some random scatter points
import matplotlib.pyplot as plt

x = np.random.randn(100)
y = np.random.randn(100)
plt.scatter(x, y)
plt.show()
```

```bash
#!/bin/bash
# Date & Joke

# Define colors
RED='\033[0;31m'; GREEN='\033[0;32m'; YELLOW='\033[1;33m'; BLUE='\033[0;34m'; MAGENTA='\033[0;35m'; CYAN='\033[0;36m'; NC='\033[0m'

# Print current date and time
echo "${GREEN}Current date and time:${NC}"
echo "${CYAN}$(date)${NC}"
echo ""

# Print a random joke
echo "${GREEN}Here's a random joke for you:${NC}"
joke=$(curl -s https://icanhazdadjoke.com/ -H "Accept: text/plain")
echo "${MAGENTA}$joke${NC}"
echo ""
```

```bash
#!/bin/bash
# System Information Script

# Define colors
RED='\033[0;31m'; GREEN='\033[0;32m'; YELLOW='\033[1;33m'; BLUE='\033[0;34m'; MAGENTA='\033[0;35m'; CYAN='\033[0;36m'; NC='\033[0m'

# Print system information
echo "${GREEN}Your system information:${NC}"
echo "${BLUE}Operating System:${NC} $(uname)"
echo "${BLUE}Hostname:${NC} $(hostname)"
echo "${BLUE}Kernel Version:${NC} $(uname -r)"
echo "${BLUE}CPU:${NC} $(lscpu | grep "Model name" | awk -F: '{print $2}' | xargs)"
echo "${BLUE}Total RAM:${NC} $(free -h --si | grep "Mem" | awk '{print $2}')"
```
