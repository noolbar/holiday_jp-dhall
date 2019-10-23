## about
japanese holidays with dhall

## generate
cat holiday_jp/holidays.yml | yaml-to-dhall ./schema.dhall

## example for yaml-to-dhall

json-to-dhall Bool <<< 'true' | dhall-to-json
json-to-dhall Bool <<< 'false' | dhall-to-json
json-to-dhall Integer <<< 2 | dhall-to-json
json-to-dhall Natural <<< 2 | dhall-to-json
json-to-dhall Double <<< -2.345 | dhall-to-json
json-to-dhall Text <<< '"foo bar"' | dhall-to-json
json-to-dhall 'List Integer' <<< '[1, 2, 3]' | dhall-to-json
json-to-dhall '{foo : List Integer}' <<< '{"foo": [1, 2, 3]}' | dhall-to-json
json-to-dhall '{foo : List Integer}' <<< '{"foo": [1, 2, 3], "bar" : "asdf"}' | dhall-to-json
json-to-dhall '{ a : Integer, b : Text }' <<< '[{"key":"a", "value":1}, {"key":"b", "value":"asdf"}]' | dhall-to-json
json-to-dhall 'List { mapKey : Text, mapValue : Text }' <<< '{"foo": "bar"}' | dhall-to-json
json-to-dhall "Optional Integer" <<< '1' | dhall-to-json
json-to-dhall '{ a : Integer, b : Optional Text }' <<< '{ "a": 1 }' | dhall-to-json
json-to-dhall 'List < Left : Text | Right : Integer >' <<< '[1, "bar"]' | dhall-to-json
json-to-dhall '{foo : < Left : Text | Right : Integer >}' <<< '{ "foo": "bar" }' | dhall-to-json
json-to-dhall '{foo : < Left : Text | Middle : Text | Right : Integer >}' <<< '{ "foo": "bar"}' | dhall-to-json
