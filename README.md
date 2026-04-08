# SE Ranking OpenAPI Specification

This repository contains [OpenAPI](https://www.openapis.org/) specifications for the [SE Ranking API](https://seranking.com/api).

Developers can use these specs to generate client libraries, explore endpoints in tools like [Swagger UI](https://swagger.io/tools/swagger-ui/) or [Redocly](https://redocly.com/), or integrate SE Ranking data into their workflows.

## Changelog

See [GitHub Releases](https://github.com/seranking/openapi/releases) for a history of spec changes.

## Directory Structure

| Directory  | Description                                                     |
| ---------- | --------------------------------------------------------------- |
| `/openapi` | The latest OpenAPI specs for all SE Ranking APIs, in JSON + YAML |

## Specs

### `/openapi`

| File              | Description                                      |
| ----------------- | ------------------------------------------------ |
| `data-api.yaml`   | SE Ranking Data API specification (YAML format)  |
| `data-api.json`   | SE Ranking Data API specification (JSON format)  |

Both files contain the same specification. Use whichever format your tooling prefers.

## Available APIs

### Data API

SEO data API providing programmatic access to:

- **Backlinks**: Backlink profiles, referring domains, anchors, authority scores, and historical trends
- **Domain Analysis**: Organic/paid keyword data, competitor research, traffic estimates, and domain authority
- **Keyword Research**: Search volume, keyword difficulty, related and long-tail keywords, SERP features
- **AI Search**: AI Overview analysis, brand monitoring in AI-generated answers, prompt-level insights
- **SERP Results**: Real-time and on-demand search engine results with full feature parsing
- **Website Audit**: Technical SEO audits with crawl data, issue detection, and page-level analysis
- **Account & System**: API key validation, rate limits, and available database regions

## Authentication

All SE Ranking API endpoints require an API key passed as a query parameter:

```
https://api.seranking.com/v1/endpoint?apikey=YOUR_API_KEY
```

Get your API key from the [SE Ranking dashboard](https://online.seranking.com/dashboard.html).

## Usage Examples

### Import in Swagger UI

Point Swagger UI at the raw spec URL:

```
https://raw.githubusercontent.com/seranking/openapi/main/openapi/data-api.yaml
```

### Generate a Client Library

Using [OpenAPI Generator](https://openapi-generator.tech/):

```bash
openapi-generator-cli generate \
  -i openapi/data-api.yaml \
  -g python \
  -o ./seranking-python-client
```

### Validate the Spec

```bash
npx @redocly/cli lint openapi/data-api.yaml
```

## OpenAPI Version

The specs use **OpenAPI 3.0**. Both JSON and YAML formats are kept in sync.

## Contributing

If you find issues with the spec (missing fields, incorrect types, documentation errors), please [open an issue](https://github.com/seranking/openapi/issues).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
