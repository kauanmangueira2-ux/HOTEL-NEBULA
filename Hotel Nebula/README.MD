# 🏨 Hotel Nebula

Modelo de banco de dados relacional para um sistema de gerenciamento hoteleiro.

---

# 📋 Descrição das Entidades

## 👤 HOSPEDE

Guarda os dados dos clientes do hotel, como nome, CPF, e-mail e telefone. Contém as informações necessárias para identificar quem irá se hospedar.

## 👨‍💼 FUNCIONARIO

Guarda os dados dos funcionários do hotel. Serve para identificar quem registrou cada reserva ou realizou cada check-in.

## 🛏️ QUARTO

Representa os quartos do hotel. Armazena informações como número do quarto, tipo, preço da diária e situação de disponibilidade, indicando se está disponível ou ocupado.

## 📅 RESERVA

Representa o agendamento realizado pelo hóspede antes de sua chegada ao hotel. Guarda a data de entrada, a data de saída e o valor total da estadia.

## 🏨 HOSPEDAGEM

Representa a entrada efetiva do hóspede no hotel após a realização do check-in. Só existe quando o hóspede realmente chega ao hotel, registrando o horário real de entrada e saída.

## 💳 PAGAMENTO

Guarda os pagamentos realizados pelo hóspede. Registra o valor pago, a forma de pagamento (cartão, PIX ou dinheiro), o status de aprovação e a nota fiscal.

## ⭐ AVALIACAO

Representa a opinião do hóspede sobre a estadia após o check-out. O hóspede pode atribuir uma nota de 1 a 5 e escrever um comentário.

---

# 🔗 Relacionamentos

## 👤 HOSPEDE → 📅 RESERVA (1:N)

Um hóspede pode realizar várias reservas, mas cada reserva pertence a apenas um hóspede.

## 🛏️ QUARTO → 📅 RESERVA (1:N)

Um quarto pode ser reservado várias vezes em períodos diferentes, mas cada reserva está associada a apenas um quarto.

## 👨‍💼 FUNCIONARIO → 📅 RESERVA (1:N)

Um funcionário pode registrar várias reservas, mas cada reserva é registrada por apenas um funcionário.

## 📅 RESERVA → 🏨 HOSPEDAGEM (1:1)

Cada reserva se transforma em uma hospedagem quando o hóspede realiza o check-in. Uma reserva pode gerar apenas uma hospedagem.

## 👨‍💼 FUNCIONARIO → 🏨 HOSPEDAGEM (1:N)

Um funcionário pode realizar o check-in de vários hóspedes, mas cada hospedagem possui apenas um funcionário responsável pelo check-in.

## 🏨 HOSPEDAGEM → 💳 PAGAMENTO (1:N)

Uma hospedagem pode possuir mais de um pagamento, por exemplo, quando o hóspede realiza pagamentos em partes. Cada pagamento pertence a apenas uma hospedagem.

## 🏨 HOSPEDAGEM → ⭐ AVALIACAO (1:1)

Cada hospedagem pode receber apenas uma avaliação. O hóspede não pode avaliar a mesma estadia mais de uma vez.

## 👤 HOSPEDE → ⭐ AVALIACAO (1:N)

Um hóspede pode realizar várias avaliações ao longo de suas estadias, mas cada avaliação é escrita por apenas um hóspede.
