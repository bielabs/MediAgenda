### História 1: Cadastro de Paciente
Como recepcionista da clínica, quero cadastrar um novo paciente no sistema, para que ele possa agendar consultas futuramente.
- Cenário: Cadastro de paciente com dados válidos<br>
  	Dado que estou na tela de cadastro de pacientes<br>
  	Quando eu preencho nome, CPF, data de nascimento, telefone e email<br>
  	E clico em "Salvar"<br>
  	Então o paciente deve ser criado com sucesso<br>
  	E deve aparecer na lista de pacientes cadastrados

### História 2: Cadastro de Médico
Como administrador do consultório, quero cadastrar um médico com sua especialidade, para que ele possa ser associado a consultas.
- Cenário: Cadastro de médico com especialidade<br>
    Dado que estou na tela de cadastro de médicos<br>
    Quando eu preencho nome, CRM, telefone, email e seleciono uma especialidade<br>
    E clico em "Salvar"<br>
    Então o médico deve ser criado com sucesso<br>
    E deve estar disponível para ser selecionado ao agendar consultas

### História 3: Agendamento de Consulta
Como paciente ou recepcionista, quero agendar uma consulta com um médico em uma data e horário específicos, para garantir o atendimento.
- Cenário 1: Agendamento de consulta em horário disponível<br>
    Dado que o médico "Dra. Ana" não possui consulta marcada às 14h do dia 10/09<br>
    Quando eu seleciono o paciente "João Silva"<br>
    E seleciono o médico "Dra. Ana" e o horário 14h do dia 10/09<br>
    E confirmo o agendamento<br>
    Então a consulta deve ser criada com status "AGENDADA"

- Cenário 2: Tentativa de agendamento em horário já ocupado<br>
    Dado que o médico "Dra. Ana" já possui uma consulta às 14h do dia 10/09<br>
    Quando eu tento agendar outra consulta para o mesmo médico no mesmo horário<br>
    Então o sistema deve exibir uma mensagem de conflito de horário<br>
    E a nova consulta não deve ser criada

### História 4: Cancelamento de Consulta
Como paciente, quero cancelar uma consulta agendada, para liberar o horário caso eu não possa comparecer.
- Cenário: Cancelamento de consulta futura<br>
    Dado que existe uma consulta "AGENDADA" para o paciente "João Silva"<br>
    Quando eu seleciono a consulta e clico em "Cancelar"<br>
    E informo o motivo do cancelamento<br>
    Então o status da consulta deve mudar para "CANCELADA"<br>
    E o horário deve voltar a ficar disponível para o médico

### História 5: Confirmação de Consulta
Como paciente, quero confirmar minha presença em uma consulta agendada, para que a clínica saiba que devo comparecer.
- Cenário: Confirmação de presença<br>
    Dado que existe uma consulta "AGENDADA" para o paciente "João Silva"<br>
    Quando eu acesso a consulta e clico em "Confirmar presença"<br>
    Então o status da consulta deve mudar para "CONFIRMADA"

### História 6: Registro de Prontuário após Consulta
Como médico, quero registrar diagnóstico e prescrição após atender um paciente, para manter o histórico clínico atualizado.
- Cenário: Registro de prontuário de consulta realizada<br>
    Dado que a consulta do paciente "João Silva" com "Dra. Ana" foi marcada como "REALIZADA"<br>
    Quando o médico preenche diagnóstico, prescrição e observações<br>
    E clica em "Salvar prontuário"<br>
    Então um novo prontuário deve ser criado, vinculado à consulta e ao paciente

### História 7: Consulta ao Histórico do Paciente
Como médico, quero visualizar o histórico de prontuários de um paciente, para ter contexto sobre atendimentos anteriores.
- Cenário: Visualização do histórico clínico<br>
    Dado que o paciente "João Silva" possui 3 prontuários registrados<br>
    Quando o médico acessa o perfil do paciente<br>
    Então deve visualizar a lista dos 3 prontuários, ordenados do mais recente para o mais antigo<br>

