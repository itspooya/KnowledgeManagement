# What is Decorator in Python?

I think one of the best answers to this question would be thinking of
a function you wrote some time ago and now want to add something to it
without either breaking it or changing structure or how it works

## Example

I have wrote a simple script to get some files and change them and then  
finally uploading it and it is OOP but then after sometime I have found
out sometimes the S3Storage which I upload files doesn't work correctly
or my network fails

I had to add a retry function to upload function responsible but nothing
seemed good until I have found out I can have a retry decorator

I have tinkered with multiple solutions and after that I was satisfied.

### Projects similar

- https://github.com/jd/tenacity
- https://pypi.org/project/retry/
