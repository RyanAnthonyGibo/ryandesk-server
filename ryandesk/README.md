# RyanDesk server

Fork do [rustdesk-server](https://github.com/rustdesk/rustdesk-server) (AGPL-3.0). Todo o crédito ao projeto RustDesk.
Código-fonte aberto neste repositório, conforme a AGPL.

Mudança: o `hbbs` aceita o registro do aparelho (`RegisterPeer`/`RegisterPk`) também por TCP/WebSocket
e guarda esse link para mandar `PunchHole`/`RequestRelay` de volta ao aparelho. Assim clientes que só
alcançam o servidor por WebSocket (por exemplo atrás de um túnel Cloudflare) ficam online e conectáveis.

Build: `docker build -f ryandesk/Dockerfile -t ryandesk-server .`
