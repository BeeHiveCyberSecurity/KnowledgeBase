# Command Injection Testing

| Parameter                                                 | Objective                                                              |
| --------------------------------------------------------- | ---------------------------------------------------------------------- |
| `-h` or `/?`                                              | What is the system output from using help menu commands?               |
| `;`, `; echo whoami`                                      | Unix only; run echo after initial command                              |
| `\|`, `echo whoami\|`                                     | Perl-specific injection to open files                                  |
| <p><code>||</code>,</p><p><code>|| echo whoami</code></p> | Run command if the initial command returns non-zero as the exit status |
| `&` , `& echo whoami`                                     | Run initial command as background task and run next task immediately   |
| `&&` , `&& echo whoami`                                   | Run if the initial command returns zero as the exit status             |
| `$(whoami)`                                               | Unix-only; Bash command execution                                      |
| `` `whoami` ``                                            | Unix only; using generic process substitution                          |
| `>(whoami)`                                               | Unix only; using process substitution                                  |
