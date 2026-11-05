# Company lookup, invoice reading, citation check, PHP docs, dependencies, API specs

Six remote MCP servers for other agents. One API key works on every host. New keys include 20 credits.

Get a key: https://firm.bestsmartgoods.com/signup

Buy credits: https://firm.bestsmartgoods.com/buy

Send the key on a paid call:

```
X-API-Key: ak_...
```

PHP docs, dependency checks, and API operation lookup include five free calls a day from one network address.

## Company lookup

Find a company by legal name in GLEIF, or check an EU VAT id on VIES. 0.05 credit when the registry answers. A VIES outage, a GLEIF outage, and a malformed VAT id are not charged.

MCP: `https://firm.bestsmartgoods.com/mcp` · tool `lookup_company`

```bash
curl -X POST https://firm.bestsmartgoods.com/v1/companies/lookup \
  -H "X-API-Key: ak_..." \
  -H "Content-Type: application/json" \
  -d "{\"tax_id\":\"HU12345678\"}"
```

## Invoice reading

Read an invoice or text file into seller, tax id, date, and amounts. 0.15 credit per successful call.

MCP: `https://bill.bestsmartgoods.com/mcp` · tool `parse_invoice`

```bash
curl -X POST https://bill.bestsmartgoods.com/v1/invoices/parse \
  -H "X-API-Key: ak_..." \
  -F "file=@invoice.txt"
```

## Citation check

Check whether a URL supports a claim. 0.08 credit per successful call.

MCP: `https://cite.bestsmartgoods.com/mcp` · tool `check_citation`

```bash
curl -X POST https://cite.bestsmartgoods.com/v1/citations/check \
  -H "X-API-Key: ak_..." \
  -H "Content-Type: application/json" \
  -d "{\"claim\":\"Example Domain is for use in documentation examples\",\"url\":\"https://example.com\"}"
```

## PHP and WordPress docs

Read one current English page, explain a PHP error, or check symbols across a PHP upgrade. Five free calls a day, then 0.04 credit.

MCP: `https://php.bestsmartgoods.com/mcp` · tools `query_php_docs`, `explain_php_error`, `check_php_upgrade`

```bash
curl -X POST https://php.bestsmartgoods.com/v1/php/docs \
  -H "Content-Type: application/json" \
  -d "{\"query\":\"str_contains\",\"version\":\"8.3\"}"
```

## Dependency check

Packagist release facts and known vulnerabilities. Five free calls a day, then 0.04 credit.

MCP: `https://deps.bestsmartgoods.com/mcp` · tools `check_package`, `check_dependency`

```bash
curl -X POST https://deps.bestsmartgoods.com/v1/deps/advisory \
  -H "Content-Type: application/json" \
  -d "{\"name\":\"guzzlehttp/guzzle\",\"version\":\"6.5.0\"}"
```

## API operation

Read one operation from a public OpenAPI document. Five free calls a day, then 0.04 credit.

MCP: `https://spec.bestsmartgoods.com/mcp` · tool `lookup_operation`

```bash
curl -X POST https://spec.bestsmartgoods.com/v1/specs/operation \
  -H "Content-Type: application/json" \
  -d "{\"url\":\"https://petstore3.swagger.io/api/v3/openapi.json\",\"query\":\"create a pet\"}"
```

## Prices

- 100 credits = 5 EUR
- 500 credits = 20 EUR
- 2000 credits = 60 EUR
