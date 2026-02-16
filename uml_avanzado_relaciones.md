classDiagram

class Cliente {
    -nombre : String
    -email : String
    +realizarPedido() : void
}

class Pedido {
    -fecha : Date
    -estado : String
    +calcularTotal() : double
}

class LineaPedido {
    -cantidad : int
    -subtotal : double
    +calcularSubtotal() : double
}

class Producto {
    -nombre : String
    -precio : double
}

%% Agregación (diamante blanco)
Cliente "1" o-- "0..*" Pedido : tiene

%% Composición (diamante negro)
Pedido "1" *-- "1..*" LineaPedido : contiene

%% Asociación
LineaPedido "0..*" --> "1" Producto : referencia
