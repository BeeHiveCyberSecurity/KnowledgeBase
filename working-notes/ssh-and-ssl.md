# SSH & SSL

OPENSSL

| Command                                                                                    | Description                                                                                 |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------- |
| `openssl s_client -connect 8.X.X.X:443 2>/dev/null \| openssl x509 -text \| grep Subject:` | Use the oPenSSL utilitiy to extrat information via the x509 command and grep for "Subject:" |

Use the OpenSSL utilitiy to extrat information via the x509 command and grep for "Subject:"

openssl s\_client -connect 8.X.X.X:443 2>/dev/null | openssl x509 -text | grep Subject:
