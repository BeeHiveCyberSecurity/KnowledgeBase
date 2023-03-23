# Static Code Analysis

Install semgrep (

[SonarQube](https://docs.sonarqube.org/latest/analyzing-source-code/overview/)

alternative):

​

[semgrep](https://semgrep.dev/docs/getting-started/)

\- static source code analyzer which works on over 25 languages

Install: `python3 -m pip install semgrep`

Add to path in zsh: `path+=('/home/kali/.local/bin') export PATH`

Analyze code: `semgrep --config auto badcode.php`
