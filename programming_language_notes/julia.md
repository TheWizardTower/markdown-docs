# [Julia][julialang]
## `String` Manipulation
### Generate markdown table from `Vector` inputs
```julia
function md_alignment(sym::Symbol)::String
    if sym == :c
        ":-:"
    elseif sym == :r
        "--:"
    else
        ":--"
    end
end
```

```julia
md_table_row(X)::String = "|$(join(X,"|"))|"
```

```julia
function markdown_table(arr::Vector, headers::Vector, alignments::Vector{Symbol}=Symbol[])::String
    arr_element_lens = length.(arr) |> unique

    length(arr_element_lens) == 1 || error("Multiple tuple lengths in array")
    arr_element_lens[1] == length(headers) || error("Tuple and header length differ")

    arr = md_table_row.(arr)

    if !isempty(alignments)
        arr_element_lens[1] == length(alignments) || error("Alignment vector differs in length from tuples or header")
        arr = append!([md_table_row(md_alignment.(alignments))], arr)
    else
        alignment_strings = md_alignment.(repeat([:l], arr_element_lens[1]))
        arr = append!([md_table_row(alignment_strings)], arr)
    end

    join(append!([md_table_row(headers)], arr), "\n")
end
```

[julialang]: https://www.julialang.org/
