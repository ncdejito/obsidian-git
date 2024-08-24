[[Program in Object-Oriented]]

Interfaces
- description of actions that an object can do
- in OOP, a description of all functions that an object must have in order to be an X
- e.g. if an object is like a light, it should have turn on and turn off
- purpose is to enforce these properties per object of type T

Why
- standardizes process function, interchangeable parts

Python:
import abc
class FeatureGenerator
    @abc.abstractmethod
    def process(self, tile, area_raster):
        pass

