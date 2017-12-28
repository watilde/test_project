# script tag
<script>alert('xss');</script>

# onerror
<img src="/404" onerror="alert('xss')" />

# javascript link
<a name="n" href="javascript:alert('xss')">link</a>

# striped javascript link
[link](javascript:alert('xss'))

# mixed javascript link
> test <a name="n"
> href="javascript:alert('xss')">link</a>
