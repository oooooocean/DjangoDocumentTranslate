
# django.shortcuts

### `render(request, template_name, context=None, content_type=None, status=None, using=None)`

Combines a given template with a given context dictionary and returns an HttpResponse object with that rendered text.

- `content_type`: The MIME type to use for the resulting document. Defaults to 'text/html'.

### `redirect(to, *args, permanent=False, **kwargs)`

Returns an `HttpResponseRedirect` to the appropriate URL for the arguments passed.

### `get_object_or_404(klass, *args, **kwargs)`

Calls `get()` on a given model manager, but it raises `Http404` instead of the model’s `DoesNotExist` exception.

- `kclass`: A Model class, a `Manager`, or a `QuerySet` instance from which to get the object.

```python
obj = get_object_or_404(MyModel, pk=1)

# 等价于
try:
    obj = MyModel.objects.get(pk=1)
except MyModel.DoesNotExist:
    raise Http404("No MyModel matches the given query.")
```

> get_list_or_404(klass, *args, **kwargs)