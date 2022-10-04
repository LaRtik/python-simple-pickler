# Python serialization library with JSON / TOML / YAML formats.

Serialize / deserialize different objects with this library.

Objects, that can be serialized into JSON / TOML / YAML files:
- Primitives (simple types such as int, str, list and so on)
- Functions (with no recursion)
- Simple classes (no meta classes and others)


**Base concept** is to store code_arguments and other information needeed to reproduce object using different types of factories (defailt str(), int(), list() and others for primitives, default "type" for classes or "types.FunctionType" for functions)

How to install?
```
git clone https://github.com/LaRtik/python-simple-pickler/
cd your-project-name
pip install python-simple-pickler/serializer
```


How to use?
```python
from serializers.PicklerFactory import PicklerCreator

yaml_pickler = PicklerCreator.create("yaml") // First thing to do: create the Pickler. Types can be "json", "toml, "yaml"

formatted = yaml_pickler.dumps(TestClass) // dump your object to a memory

file = open("formatted.yaml", "w")
yaml_pickler.dump(file, f) // dump your object to a file
...
...
...
unformatted = yaml_pickler.loads(formatted) // load your object from a memory

file = open('formatted.yaml', "r") // load your object from a file
unformatted = yaml_pickler.load(file)
```

