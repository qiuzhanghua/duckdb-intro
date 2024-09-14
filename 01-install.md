# Install DuckDB

## From Web Site

https://duckdb.org/docs/installation/

## TDP Manner

### 0. 前提条件

- Linux/darwin
- TDP Cli 24.x installed
- Python 3 installed

### 1. 克隆 tdp-script

```bash
git clone https://git.taiji.com.cn:8888/tj/tdp-scripts.git
```

### 2. 进入目录

```bash
cd tdp-scripts
```

### 3. 生成 DuckDB 的插件(适用于 TDP)

- 查看能为哪些操作系统生成

```bash
./pack-duckdb.py --help
```

结果类似：

<pre>
Usage: pack-duckdb.py [OPTIONS]

Options:
  -p, --platform [linux|windows|darwin]
                                  Operating System
  -a, --arch [amd64|arm64|universal]
                                  CPU Architecture
  -v, --version [1.0.0|1.1.0]     duckdb cli Version
  -k, --packer TEXT               Packer
  --help                          Show this message and exit.
</pre>

#### 1). 为 Linux 生成

```bash
./pack-duckdb.py -v 1.1.0
```

会生成

> ./plugin/duckdb_1.1.0_linux_amd64.tar.gz

如果要生成 ARM64 版本的，则运行

```bash
./pack-duckdb.py -v 1.1.0 -a arm64
```

生成

> ./plugin/duckdb_1.1.0_linux_arm64.tar.gz

#### 2). 为 Window 生成

```bash
./pack-duckdb.py -p windows -v 1.1.0
```

会生成

> ./plugin/duckdb_1.1.0_windows_amd64.tar.gz

如果要生成 ARM64 版本的，则运行

```bash
./pack-duckdb.py -p windows -v 1.1.0 -a arm64
```

生成

> ./plugin/duckdb_1.1.0_windows_arm64.tar.gz

#### 3) 为 Mac 生成

```bash
./pack-duckdb.py -p darwin -v 1.1.0
```

会生成

> ./plugin/duckdb_1.1.0_darwin_amd64.tar.gz

如果要生成 ARM64 版本的，则运行

```bash
./pack-duckdb.py -p darwin -v 1.1.0 -a arm64
```

生成

> ./plugin/duckdb_1.1.0_darwin_arm64.tar.gz

#### 4）生成时如果报错，则 Python 需要先安装一些组件，类似

```bash
pip install wget click
```

### 4. 安装 DuckDB

```bash
tdp i plugin/duckdb_1.1.0_your-os_your-cpu.tar.gz
```

并重新启动 Terminal.

[配置 vscode](02-vscode.md) | [返回](README.md)
