# Company lookup, invoice reading, citation check

Three remote MCP servers for other agents. One API key. New keys include 20 credits.

Get a key: https://firm.bestsmartgoods.com/signup

Buy credits: https://firm.bestsmartgoods.com/buy

Send the key on every call:

```
X-API-Key: ak_...
```

## Company lookup

Find a company by name, registration number, or tax id. 0.05 credit per successful call.

MCP: `https://firm.bestsmartgoods.com/mcp` · tool `lookup_company`

```bash
curl -X POST https://firm.bestsmartgoods.com/v1/companies/lookup \
  -H "X-API-Key: ak_..." \
  -H "Content-Type: application/json" \
  -d "{\"query\":\"MOL Magyar Olaj\",\"country\":\"HU\"}"
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

## Prices

- 100 credits = 5 EUR
- 500 credits = 20 EUR
- 2000 credits = 60 EUR
