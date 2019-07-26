----------------------- array 1----------------------- 
Array
(
    [0] => FirSt
    [1] => SecOnd
    [2] => ThiRD
    [3] => 0
    [4] => 1
)
----------------------- array 2----------------------- 
Array
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => Array
        (
            [id] => 2135
            [first_name] => John
            [last_name] => Doe
        )

    [4] => Array
        (
            [id] => 3245
            [first_name] => Sally
            [last_name] => Smith
        )

)
----------------------- array_combine ----------------------- 
Array
(
    [FirSt] => 1
    [SecOnd] => 2
    [ThiRD] => 3
    [0] => Array
        (
            [id] => 2135
            [first_name] => John
            [last_name] => Doe
        )

    [1] => Array
        (
            [id] => 3245
            [first_name] => Sally
            [last_name] => Smith
        )

)
----------------------- array_change_key_case ----------------------- 
Array
(
    [FIRST] => 1
    [SECOND] => 2
    [THIRD] => 3
    [0] => Array
        (
            [id] => 2135
            [first_name] => John
            [last_name] => Doe
        )

    [1] => Array
        (
            [id] => 3245
            [first_name] => Sally
            [last_name] => Smith
        )

)
----------------------- array_chunk ----------------------- 
Array
(
    [0] => Array
        (
            [0] => 1
            [1] => 2
        )

    [1] => Array
        (
            [0] => 3
            [1] => Array
                (
                    [id] => 2135
                    [first_name] => John
                    [last_name] => Doe
                )

        )

    [2] => Array
        (
            [0] => Array
                (
                    [id] => 3245
                    [first_name] => Sally
                    [last_name] => Smith
                )

        )

)
----------------------- array_column ----------------------- 
Array
(
    [0] => Doe
    [1] => Smith
)
----------------------- array_count_values ----------------------- 
Array
(
    [0] => 1
    [1] => 1
    [2] => 1
    [3] => 2
    [4] => 3
    [5] => 3
)
Array
(
    [1] => 3
    [2] => 1
    [3] => 2
)
----------------------- array_diff_assoc ----------------------- 
Array
(
    [0] => blue
    [1] => red
    [2] => pink
)
Array
(
    [0] => green
    [1] => blue
    [2] => red
)
----------------------- output ----------------------- 
Array
(
    [0] => blue
    [1] => red
    [2] => pink
)
----------------------- array_diff_key ----------------------- 
Array
(
    [0] => blue
    [1] => red
    [2] => pink
    [section1] => one
)
Array
(
    [0] => green
    [1] => blue
    [2] => red
    [section2] => two
)
----------------------- output ----------------------- 
Array
(
    [section1] => one
)
Array
(
    [3] => Perry
)
