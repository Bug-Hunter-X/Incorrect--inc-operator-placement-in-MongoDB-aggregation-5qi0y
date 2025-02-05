# Incorrect $inc operator placement in MongoDB aggregation
This example demonstrates an incorrect usage of the `$inc` operator within a MongoDB aggregation pipeline. The `$inc` operator is intended to increment a field's value. However, it's incorrectly placed outside the context of a `$group` stage or another suitable operation. This leads to unintended results or errors.

**Problem:** The `$inc` operator is used after a `$group` stage.  Instead of incrementing values within each grouped document, it adds 1 to every document.  This means the `count` will be inflated to reflect the total number of groups + 1 per document.

**Solution:** Move the increment operation inside the `$group` stage using the `$sum` operator.
