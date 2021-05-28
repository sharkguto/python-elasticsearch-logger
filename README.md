# Logger ES handler

## about

It is a derivated project from [CMRESHandler](https://github.com/cmanaha/python-elasticsearch-logger) module.

I did it because poetry does not work dependencies with fork projects.

```bash
poetry publish -vvv

Username: 
Password: 
Publishing logger-es-cli (0.3.0) to PyPI
 - Uploading logger-es-cli-0.3.0.tar.gz 100%

  Stack trace:

  7  /usr/lib/python3.9/site-packages/clikit/console_application.py:131 in run
      129│             parsed_args = resolved_command.args
      130│ 
    → 131│             status_code = command.handle(parsed_args, io)
      132│         except KeyboardInterrupt:
      133│             status_code = 1

  6  /usr/lib/python3.9/site-packages/clikit/api/command/command.py:120 in handle
      118│     def handle(self, args, io):  # type: (Args, IO) -> int
      119│         try:
    → 120│             status_code = self._do_handle(args, io)
      121│         except KeyboardInterrupt:
      122│             if io.is_debug():

  5  /usr/lib/python3.9/site-packages/clikit/api/command/command.py:171 in _do_handle
      169│         handler_method = self._config.handler_method
      170│ 
    → 171│         return getattr(handler, handler_method)(args, io, self)
      172│ 
      173│     def __repr__(self):  # type: () -> str

  4  /usr/lib/python3.9/site-packages/cleo/commands/command.py:92 in wrap_handle
       90│         self._command = command
       91│ 
    →  92│         return self.handle()
       93│ 
       94│     def handle(self):  # type: () -> Optional[int]

  3  /usr/lib/python3.9/site-packages/poetry/console/commands/publish.py:77 in handle
      75│         )
      76│ 
    → 77│         publisher.publish(
      78│             self.option("repository"),
      79│             self.option("username"),

  2  /usr/lib/python3.9/site-packages/poetry/publishing/publisher.py:93 in publish
      91│         )
      92│ 
    → 93│         self._uploader.upload(
      94│             url,
      95│             cert=cert or get_cert(self._poetry.config, repository_name),

  1  /usr/lib/python3.9/site-packages/poetry/publishing/uploader.py:119 in upload
      117│ 
      118│         try:
    → 119│             self._upload(session, url, dry_run)
      120│         finally:
      121│             session.close()

  UploadError

  HTTP Error 400: Invalid value for requires_dist. Error: Can't have direct dependency: 'cmreshandler @ git+https://github.com/sharkguto/python-elasticsearch-logger@master'

  at /usr/lib/python3.9/site-packages/poetry/publishing/uploader.py:216 in _upload
      212│                     self._register(session, url)
      213│                 except HTTPError as e:
      214│                     raise UploadError(e)
      215│ 
    → 216│             raise UploadError(e)
      217│ 
      218│     def _do_upload(
      219│         self, session, url, dry_run=False
      220│     ):  # type: (requests.Session, str, Optional[bool]) -> None
```

## thanks

Thank you for share it, Carlos Manzanedo Rueda!
