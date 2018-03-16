---
permalink: sql-server
---

## SqlBulkCopyOptions
Gets or sets the SqlBulkCopyOptions to use when `SqlBulkCopy` is used to directly insert in the destination table.

{% include template-example.html %} 
{% highlight csharp %}
context.BulkSaveChanges(options =>
{
   options.SqlBulkCopyOptions = SqlBulkCopyOptions.Default | SqlBulkCopyOptions.TableLock;
});
{% endhighlight %}
