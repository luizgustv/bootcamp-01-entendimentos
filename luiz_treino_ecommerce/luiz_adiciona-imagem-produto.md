MultipartFile - interface do Spring para trabalhar com arquivos

@ElementCollection
@OneToMany

https://medium.com/@sakshikhandelwal276/elementcollection-vs-onetomany-in-hibernate-7fb7d2ac00ea

Comparison:
@ElementCollection on the other hand, is very similar to @OneToMany except target object is not an Entity.
With @ElementCollection, we can’t query, persist or merge target object independently of their parent object.
It doesn’t support cascade operation. It means target object are always persisted, merged, removed with their parent object.
So, @ElementCollection is an easy way to define a collection with simple/basic objects. @ OneToMany is the best for complex use-case 
in which fine-grained control is required.

ResponseStatusException 403 - tratar exceção (em CapturaExceptionHandler)
- que mensagem por? O produto não é seu?