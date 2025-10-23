# Blog Aggregator CLI

This is a command-line interface (CLI) for aggregating blog posts.

## Prerequisites

To run this program, you will need the following installed on your system:

*   **PostgreSQL**: This project uses PostgreSQL as its database. You'll need an active PostgreSQL instance and its connection details.
*   **Go**: The project is written in Go, so you'll need a Go development environment (version 1.22 or higher is recommended).

## Installation

### Install the `blogagg` CLI

You can install the `blogagg` CLI tool using `go install`:

```sh
go install github.com/jcgoodwin86/blogagg@latest
```

This command will download, compile, and install the `blogagg` executable into your Go binary path (typically `$GOPATH/bin`). Make sure your `$GOPATH/bin` is in your system's `PATH` to run `blogagg` directly from your terminal.

## Configuration

Before running the program, you need to set up a configuration file. The CLI expects a `config.json` file in the directory where you run the commands.

Here's an example `config.json` file:

```json
{
  "db_url": "postgresql://user:password@host:port/database?sslmode=disable",
  "current_user_name": ""
}
```

*   `db_url`: Replace `postgresql://user:password@host:port/database?sslmode=disable` with your actual PostgreSQL connection string.
*   `current_user_name`: This field will be updated by the CLI after you log in or register a user. You can leave it empty initially.

## Usage

Once installed and configured, you can run `blogagg` commands from your terminal.

Here are a few example commands:

*   **Register a new user**:
    ```sh
    blogagg register <username> <password>
    ```

*   **Log in an existing user**:
    ```sh
    blogagg login <username> <password>
    ```

*   **Add a new feed**: (Requires being logged in)
    ```sh
    blogagg addfeed <name> <url>
    ```

*   **List all feeds**:
    ```sh
    blogagg feeds
    ```

*   **Browse posts from followed feeds**: (Requires being logged in)
    ```sh
    blogagg browse
    ```
