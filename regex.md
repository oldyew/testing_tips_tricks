# REGEX

```regex

/407|321/ # or
/ar+/ # 1 or more 'r'
/[a-z]+/ # 1 or more character set
/[a-z]+/i # i modifier means case insensative
/test\stest/ # \s means spaces, tabs, new lines
/[a-z\s]+/i
\w == [a-zA-Z0-9]
/\w\s/
. # metacharacter for any symbol except newline
\. # for dot only
\+ # for plus only
? # make proceeding pattern optional
\? # for quation only

/\w+@\w+\.(com|org|net)/i # sara@example.com
^ # start looking
$ # stop looking
/^\w+@\w+\.(com|org|net)$/i

\b # boundary metacharacter
/\b\w+\b/ # learn by doing

/ship?/ # p is 0 or 1 times
/\bok(ay)?\b/i # ok or okay
/\b(ok(ay)?|sure)\b/i # ok and sure, but not unsure
/\b(ok(ay)?|sure|y(es)?)\b/i # ok, okay, sure, yes and y

^ # not
\d # number
[^\d] == \D # every except number
[^\s] == \S # every except whitespaces
[^\w] == \W # every except words

{2,20} # min and max characetrs

/penguin/ig # g is global modifier means each occurance

/^\w+\spenguin$/mig # m is multiline modifier

/^\w+\s(penguin|tern)$/mig

\d+\s[\w\s]+\w{4,6},\s # street. "12 Test lane,"
[\w\s]+,\s # city
\w{2}\s # state
\d{5} # zip
/^\d+\s[\w\s]+\w{4,6},\s[\w\s]+,\s\w{2}\s\d{5}$/ig # full address

/^(\d+\s[\w\s]+(?:street|lane)),\s([\w\s]+),\s(\w{2})\s(\d{5})$/ig # groups = address + city + state + zip

