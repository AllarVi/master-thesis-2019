# Some useful bash commands

## Echo files
ls | grep -i rasmus | xargs -I {} echo {}

## Delete
ls | grep -i rasmus | xargs -I {} rm {}