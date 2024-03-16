# Evaluator Button Labels

In a toolbar or menu button, you can use the **@label** modifier to set the button label dynamically using the evaluator.

As a very basic example, \<ib:inline-code\>`@label:=return "Hello!";`\</ib:inline-code\> would set the label to "Hello!".

![](page>standard_variables&nodate&nouser&nofooter)

The original label is available as the \<ib:inline-code\>`original_label`\</ib:inline-code\> variable.

The return value from the evaluation expression will be used as the label for the button.
