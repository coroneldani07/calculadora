classDiagram

class Cliente {
  -String nombre
  -String email
  +realizarPedido()
}

class Pedido {
  -Date fecha
  -String estado
  +calcularTotal()
}

class LineaPedido {
  -int cantidad
  -double subtotal
  +calcularSubtotal()
}

class Producto {
  -String nombre
  -double precio
}

Cliente "1" o-- "0..*" Pedido
Pedido "1" *-- "1..*" LineaPedido
LineaPedido "0..*" --> "1" Producto

