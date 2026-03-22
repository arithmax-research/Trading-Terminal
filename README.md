# Trading Terminal

## Introduction

This repository is a Trading Terminal customized to use OpenBB-style backend integrations. Whether hosted internally or externally, this approach provides a standardized structure that terminal widgets can read and display.

Note: most examples use Python FastAPI because it is the stack we know best, but you can implement the same pattern in other languages.

The main backend integration tenets are:

1. **Return data in JSON format** (if your response is nested, you can use the `dataKey` field in `widgets.json`).

<details>
    <summary>Example JSON</summary>

    ```json
    [
      {
        "ticker": "AAPL",
        "name": "Apple Inc.",
        "price": 150.5,
        "marketCap": 2500000000,
        "change": 1.25
      },
      {
        "ticker": "GOOGL",
        "name": "Alphabet Inc.",
        "price": 2800.75,
        "marketCap": 1900000000,
        "change": -0.75
      },
      {
        "ticker": "MSFT",
        "name": "Microsoft Corporation",
        "price": 300.25,
        "marketCap": 220000000,
        "change": 0.98
      }
    ]
    ```

</details>

2. **Expose an endpoint that returns `widgets.json`**: this file defines widget properties such as name, description, category, type, endpoint, and related metadata. Each widget is defined in this file. You can find examples in the template folders and a detailed definition below.

3. **Enable CORS**: if you host locally, you must enable [CORS](https://fastapi.tiangolo.com/tutorial/cors/).

4. **Authentication (optional)**: if your backend requires authentication, you can configure a query parameter or header when connecting through OpenBB Pro. These values are sent on every request once configured. If you need another authentication method, please reach out to us.

## Getting Started

We recommend this order:

1. Start with [getting-started/hello-world](getting-started/hello-world/README.md).
2. Continue with [getting-started/reference-backend](getting-started/reference-backend/README.md).

These examples provide a strong foundation for setting up your own backend and connecting it to the Trading Terminal widget ecosystem.

### Leveraging AI

If you are using a coding agent to build your OpenBB backend, we recommend:

- Using the OpenBB docs MCP server: [https://smithery.ai/server/@DidierRLopes/openbb-docs-mcp](https://smithery.ai/server/@DidierRLopes/openbb-docs-mcp)
- Or providing full docs context in markdown format: [https://docs.openbb.co/workspace/llms-full.txt](https://docs.openbb.co/workspace/llms-full.txt)

For more examples and guides, visit [https://docs.openbb.co/workspace](https://docs.openbb.co/workspace).

## Examples of Apps

Explore open-source OpenBB apps built by the team and community: [https://github.com/OpenBB-finance/awesome-openbb](https://github.com/OpenBB-finance/awesome-openbb).