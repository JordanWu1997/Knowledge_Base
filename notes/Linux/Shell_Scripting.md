# Shell Scripting

subshell (...)

- Variables will not be saved

grouping {...}

- Variables will be saved

backticks \`\`

- Save result as variables

process substitution \<() ()>

- Use subshell output as standard input/output

redirect standard input/output/error
\<
1>
2>
&>

${var_name:-default_value}
${var_name:=default_value}
${var_name:?default_value}

$((  ))

echo

EOF
IFS

RANDOM

> >

trap

wait
