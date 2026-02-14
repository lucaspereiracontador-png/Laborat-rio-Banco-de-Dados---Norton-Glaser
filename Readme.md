Entidades e Atributos
Leitor
id_leitor (PK)

  nome
  endereço
  cidade
  estado
  telefone
  email
  documento_identificação
  data_nascimento
  id_categoria_leitor (FK)

Categoria_Leitor

  id_categoria_leitor (PK)
  descrição
  max_dias_emprestimo
  
Obra

  id_obra (PK)
  ISBN
  título
  id_categoria_obra (FK)
  autores
  palavras_chave
  data_publicação
  edição
  editora
  num_paginas

Categoria_Obra

  id_categoria_obra (PK)
  descrição
  taxa_diaria_atraso
  
Cópia

  id_copia (PK)  
  id_obra (FK)  
  status (disponível/emprestada/reservada)

Funcionário

  id_funcionario (PK)
  nome
  endereço
  cidade
  estado
  telefone
  data_nascimento

Reserva

  id_reserva (PK)  
  data_reserva  
  data_prevista_retirada  
  data_prevista_devolucao  
  id_leitor (FK)  
  id_obra (FK)  
  id_funcionario (FK)

Empréstimo

  id_emprestimo (PK)  
  data_emprestimo  
  data_prevista_devolucao  
  id_leitor (FK)  
  id_funcionario (FK)  
  id_copia (FK)

Devolução

  id_devolucao (PK)  
  id_copia (FK)  
  data_devolucao  
  multa (calculada com base na categoria da obra e dias de atraso)

Relacionamentos
Leitor → Categoria_Leitor: muitos leitores pertencem a uma categoria.

Obra → Categoria_Obra: muitas obras pertencem a uma categoria.

Obra → Cópia: uma obra pode ter várias cópias.

Reserva → Leitor / Obra / Funcionário: cada reserva está ligada a um leitor, uma obra e um funcionário.

Empréstimo → Leitor / Funcionário / Cópia: cada empréstimo envolve um leitor, um funcionário e uma cópia específica.

Devolução → Cópia: cada devolução está ligada a uma cópia emprestada.




