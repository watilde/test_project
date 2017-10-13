`aria-relevant` indicates what types of changes should be presented to the user.
There are some options that may be used separately or as a token list.

 - *additions*, meaning that any element being added to the live region is
   significant. For example, appending a span to an existing log of status
   messages would mean that the span would be announced to the user (assuming
   that `aria-atomic` was `false`).
 - *text*, meaning that text content being added to any descendant node is
   relevant. For example, modifying a custom text field's `textContent` property
   would read the modified text to the user.
 - *removals*, meaning that the removal of any text or descendant nodes should
   be conveyed to the user.
 - *all*, meaning that all changes are relevant. However, the default value for
   `aria-relevant` is `additions text`, meaning that if you don't specify
   `aria-relevant` it will update the user for any addition to the element,
   which is what you are most likely to want.
