# Release notes

## Python 3 port

- Ported `soda.py` to Python 3 (the script previously targeted Python 2): `Retry`
  import path, string/bytes handling in cartDump parsing and region ID encoding,
  `zip()` materialization, and text-mode writing of the gallery index.
- Replaced the ImageMagick + Ghostscript PDF→PNG/thumbnail pipeline with
  [PyMuPDF](https://pypi.python.org/pypi/PyMuPDF), which bundles its own renderer and
  requires no system tools. ImageMagick `convert`/`identify` are now only required for
  the optional interval/midpoint annotation overlays (`-i`/`-d`).
- Made `requests-kerberos` an optional import so the tool runs on hosts without krb5
  development headers. Browser instances that accept HTTP Basic auth (e.g. SSO/AD with a
  `Basic` realm) work via `-u`/`-p` with no Kerberos dependency.
- Added `requirements.txt` and ignore the `.venv/` directory.

## Current

- To avoid empty galleries, web requests for UCSC Genome Browser cart data are retried, if the response is chunked (incomplete response from server) or lacks PDF-related links (perhaps the server is slow).
- Soda warns about and skips over blank regions in the input BED file, if found.
- Soda re-encodes ID fields from UTF-8 to ASCII, to avoid template rendering issues from non-ASCII characters.
- UI improvements for thumbnail table, in order to help with browsing a larger set of input regions.

## soda/20170113

- Default module prior to this commit point.