# Defining a Filter

A filter is constructed from one or more *clauses*: instructions to compare a particular attribute of a file with the provided values. When Opus applies a filter to an operation, every potential file that the operation could affect is compared against the clauses in the filter, and the file is only processed if it matches the filter.

Filters are effectively Boolean operations expressed in human-readable form.

- Individual clauses can be set to *Match* (true)* *or *No Match* (false), which give the effect of a **not** operator.
- Clauses are linked with the Boolean operators **and** or **or**.
- A filter can also have sub-clauses, which give the effect of parentheses in Boolean operations.

For example, consider the following Boolean expression. The effect of this is to match all **.jpg** files that are larger than 100KB or all **.gif** files that are smaller than 50KB (quite why you'd want to do that is another question):

    ( Name matches *.jpg and size > 100KB ) or
    ( Name matches *.gif and size < 50KB )

This would be represented in a filter control by the following clauses:

![](/Manual/images/media/complex_filter.png) 

The two expressions enclosed in parentheses are represented by sub-clauses. Each sub-clause contains two clauses linked by **and** operators; a **Name** match which compares the filename against a wildcard pattern, and a **Size** match which compares the size of the file against a given value. Finally the two sub-clauses are linked by an **or** operator. You can see that in the filter control the contents of sub-clauses are indented from their parent clause.

In the above example, all the clauses are set to *Match* which means the condition in the clause must be **true** for it to match. If a clause is set to *No Match* then it must be **false** for the clause to match. Imagine if we wanted to match all **.jpg** files that are larger than 100KB, but **not** those that are larger than 1MB or have the word "horse" in their name. The human-readable form of this would be:

    Name matches *.jpg and size > 100KB and
    not ( size > 1MB or name contains "horse" )

In the filter control you could represent this in the following way:

![](/Manual/images/media/complex_filter_2.png) 

The sub-clause in the above example is set to *No Match* meaning the filter won't match a file unless sub-clause **fails** to match. The sub-clause contains two child clauses, both of which are set to *Match* and linked by the **or** operator. So for the file in question, if its **Size** is greater than 1 MB or its **Name** contains "horse", one or other (or both) of those clauses will match, which means its parent sub-clause will match, which means (because the sub-clause was set to *No Match*) the filter will fail. Confused yet? :)
