\Software: Rede Social da Universidade

Requisitos não funcionais:

1 - O software deve funcionar na web

2 - O software deve funcionar em tablets e smartphones



Requisitos Funcionais - Lista de caso de uso:

UC01 - Acesso ao Sistema

UC02 - Cadastro do Usuário

UC03 - Postar Vagas

UC04 - Postar treinamentos

UC05 - Consulta postagens

UC06 - Obter informações de postagens

UC07 - Cadastro do curso do aluno



Descrição dos casos de uso:

Nome:UC02 - Cadastro do Usuário

Breve descrição: O caso de uso deve incluir, permitir alterar, consultar ou excluir usuário.A exclusão
do usuário deve ser uma exclusão lógica, alterando o status para "inativo".

Pré-condição: Inclusão - ele não pode ter sua matrícula cadastrada.Consulta, alteração ou exclusão - Usuário deve estar logado no sistema.

Fluxo Principal:

Inclusão de usuário novo:

	 1 - Usuário Informa matricula
	 2 - Sistema verifica se matrícula contém 6 digitos.
	 3 - Se matrícula não tem 6 digitos, chamar FA01
	 4 - Verificar se matricula é existente na tabela USUARIO
	 5 - Se matricula existente, enviar msg "Usuário já cadastrado"; chamar UC01
	 6 - Usuário informar senha
	 7 - Sistema verifica RN01
	 8 - Se senha não OK, Chamar FA02
	 9 - Usuário informa email
	 10 - Se email não possui @, chamar MSG01
	 11 - Usuário informa número celular
	 12 - Se número de celular não tem 8 digitos e não tem código de área, chama MSG02
	 13 - Grava "ATIVO" no campo status.
	 14 - Salvar novo usuário

Consultar usuário:
	
	1 - Apresentar tela com dados do usuário, filtrado na tabela de USUARIO através da matricula.
	2 - Verificar se status do usuário está = "INATIVO"
	3 - Se sim, mostrar a msg " Usuário INATIVO".
	
Alterar dados do usuário:

	1 - Alterar senha
	2 - Sistema verifica RN01
	3 - Se senha não OK, Chamar FA02
	4 - Usuário altera email
	5 - Se email não possui @, chamar MSG01
	6 - Usuário altera número celular
	7 - Se número de celular não tem 8 digitos e não tem código de área, chama MSG02
	8 - Salvar novo usuário

Excluir usuário:
	
	1 - Enviar msg "Deseja realmente excluir usuário (S/N)"
	2 - Se S, gravas status do usuari como "INATIVO"
	3 - Salvar exclusão de usuário.	

Fluxo Alternativo:

	FA01 - Enviar msg "Matricula Inválida" Voltar para UC02
	FA02 - Envisar msg "Senha Inválida.Defina uma senha que contenha:no mínimo 8 dígitos, sendos pelos menos 1 letra maiúscula, 1 carácter especial e 1 número."

Mensagens:

	MSG01 - Email inválido
	MSG02 - Número de celular Inválido

Regras de Negócio:

	RN01 - Senha deve conter no mínimo 8 dígitos, sendos pelos menos 1 letra maiúscula, 1 carácter especial e 1 número.
