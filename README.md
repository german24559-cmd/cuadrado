from abc import ABC, abstractmethod
import math

class Figura(ABC):
    @abstractmethod
    def calcular_perimetro(self) -> float:
        pass

    @abstractmethod
    def calcular_area(self) -> float:
        pass

    @abstractmethod
    def obtener_nombre(self) -> str:
        pass

class Circulo(Figura):
    def __init__(self, radio: float):
        self.radio = radio

    def calcular_perimetro(self) -> float:
        return 2 * math.pi * self.radio

    def calcular_area(self) -> float:
        return math.pi * (self.radio ** 2)

    def obtener_nombre(self) -> str:
        return "Círculo"

c = Circulo(5)
print(c.obtener_nombre())
print(f"Perímetro: {c.calcular_perimetro():.2f}")
print(f"Área: {c.calcular_area():.2f}")
