### Project description

## 🚀 What is PYHDL?

**PYHDL** is a revolutionary `.pyhd` to `.vhd` converter that empowers software developers to write hardware designs using familiar Python syntax. No more steep learning curve for VHDL—write `.pyhd` files, get industry-standard `.vhd` output.

### 📁 File Types

- **`.pyhd`** - PYHDL source files (Python-like hardware description)
- **`.vhd`** - VHDL output files (industry-standard hardware description)


### Updated command reference


## 💻 Command Reference

### Basic Usage

```bash
# Convert .pyhd to .vhd
pyhdl <input.pyhd> <output.vhd>
```
```bash
# Examples
pyhdl counter.pyhd counter.vhd
pyhdl multiplexer.pyhd mux.vhd
pyhdl processor.pyhd processor.vhd
```

### File Extension Details

**Input Files (`.pyhd`):**
- PYHDL source code with Python-like syntax
- Hardware description in a developer-friendly format
- Processed and converted to VHDL

**Output Files (`.vhd`):**
- Standard VHDL compliant code
- Ready for synthesis tools
- Industry-standard format
## 💻 Quick Start

### 🎯 Installation in 3 Steps

```bash
# 1. Clone the repository
git clone https://github.com/pyhdl/pyhdl.git
cd pyhdl

# 2. Build the Debian package
chmod +x build_deb.sh
./build_deb.sh

# 3. Install
sudo dpkg -i pyhdl_0.1.0-1_amd64.deb
sudo apt-get install -f
```

### 🎬 Your First Conversion

**Input file: `counter.pyhd`**
```python
entity Counter(
    clock: std_logic, 
    reset: std_logic
) -> count: std_logic_vector(7 downto 0):
    
    process counter_proc(clock, reset):
        if reset = '1':
            count <= X"00"
        elif rising_edge(clock):
            count <= count + 1
        end if
    end process
```

**Command:**
```bash
pyhdl counter.pyhd counter.vhd
```

**Output file: `counter.vhd`**
```vhdl
entity Counter is
    port(
        clock: in std_logic;
        reset: in std_logic;
        count: out std_logic_vector(7 downto 0)
    );
end entity Counter;

architecture CounterArch of Counter is
begin
    process counter_proc(clock, reset) is
    begin
        if reset = '1' then
            count <= X"00";
        elsif rising_edge(clock) then
            count <= count + 1;
        end if;
    end process;
end architecture CounterArch;
```

✨ **Just like that!**


### Usage section


## 📖 Usage

### Command Syntax

```bash
pyhdl <input.pyhd> [output.vhd] [options]
```

### Arguments

| Argument | Description |
|---------|-------------|
| `input.pyhd` | Input PYHDL file (`.pyhd` extension) |
| `output.vhd` | Output VHDL file (`.vhd` extension, default: `out.vhd`) |
| `--verbose, -v` | Enable verbose output |

### Examples

```bash
# Basic conversion (.pyhd → .vhd)
pyhdl design.pyhd design.vhd

# Output to default file (out.vhd)
pyhdl design.pyhd

# With verbose output
pyhdl design.pyhd design.vhd --verbose

# Short flag
pyhdl design.pyhd design.vhd -v
```

### File Extensions

| Type | Extension | Description |
|------|-----------|-------------|
| **Input** | `.pyhd` | Python-like hardware description files |
| **Output** | `.vhd` | Standard VHDL output files |
```

### Updated examples throughout

**Example 1:**
```bash
pyhdl mydesign.pyhd mydesign.vhd
```

**Example 2:**
```bash
# Create counter.pyhd
pyhdl counter.pyhd counter.vhd

# Create mux.pyhd
pyhdl mux.pyhd mux.vhd
```
