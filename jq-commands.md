Check values and unique them:

`curl https://open.vhb.org/oersi.json | jq '[.data[].attributes.subjectarea] | unique'`

Check instant schema: (but result is not good enough)

`curl https://open.vhb.org/oersi.json | jq 'path(..) | map(tostring) | join ("/")'`
`curl https://open.vhb.org/oersi.json | jq '.data[]| path(..) | map(tostring) | join ("/")'`


Instant schema /path but unique
`curl https://open.vhb.org/oersi.json | jq '[.data[]]| select(objects)|=[.] | map( paths(scalars) ) | map( map(select(numbers)="[]") | join(".")) | unique'`


