# Compare the Triplets

https://www.hackerrank.com/challenges/compare-the-triplets/problem

```php
<?php

// Complete the compareTriplets function below.
function compareTriplets($a, $b) {
    $length = count($a);
    $aliceScore = 0;
    $bobScore = 0;
    for($i=0; $i<$length; $i++){
        if($a[$i] == $b[$i]){
            continue;
        }
        if($a[$i] > $b[$i]){
            $aliceScore++;
            continue;
        }
        $bobScore++;
    }
    return [$aliceScore, $bobScore];
}

$fptr = fopen(getenv("OUTPUT_PATH"), "w");
$a_temp = rtrim(fgets(STDIN));
$a = array_map('intval', preg_split('/ /', $a_temp, -1, PREG_SPLIT_NO_EMPTY));
$b_temp = rtrim(fgets(STDIN));
$b = array_map('intval', preg_split('/ /', $b_temp, -1, PREG_SPLIT_NO_EMPTY));
$result = compareTriplets($a, $b);
fwrite($fptr, implode(" ", $result) . "\n");
fclose($fptr);

```
