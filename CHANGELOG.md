# Release notes

## Current

- To avoid empty galleries, web requests for UCSC Genome Browser cart data are retried, if the response is chunked (incomplete response from server) or lacks PDF-related links (perhaps the server is slow).
- Soda warns about and skips over blank regions in the input BED file, if found.
- Soda re-encodes ID fields from UTF-8 to ASCII, to avoid template rendering issues from non-ASCII characters.
- UI improvements for thumbnail table, in order to help with browsing a larger set of input regions.

## soda/20170113

- Default module prior to this commit point.