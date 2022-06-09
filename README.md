Spring Framework

Data Accses - Transações com banco de dados
Web - permite criar aplicações web
AOP - Programação Orientada a Aspectos
Instrumentação

Core Container - onde está a implementação da inversão de controle

Invesão de Controle - padrão de projeto, em que um objeto apenas declara suas
 dependências sem cria-las e delegas a tarefa de construir tais dependências
  a um Container IoC (Core Container).
  
Injeção de Dependências (Implementação da inversão de controle)
Implementação utilizada pelo Spring Framework de aplicar a Inversão de Controle
 quando necessário

Bean
é um objeto instanciado, montado e gerenciado por um container do Spring atravéz
 da Inversão de Controle (Ioc) e Injeção de Dependências
 Exemplo de Esteriótipos do Spring: @Component, @Service, @Repository, @Controller.


Spring Boot
Spring Boot = Spring Framework + Servidor Embutido(Tomcat) - @Configuration (Arquivos e classes de configurações)



*Models*
@Entity - mostrar pro JPA que é uma entidade
@Table - nome que a entidade vai ter no banco de dados
Serializable - 
@Id - por ser um entidade necessita de um identificador
UUID - 
@Column - passar as restrições quando as colunas forem criadas no banco de dados


*Repository*
@Repository - 


*Service*
@Service - 
Formas de criar ponto de injeção
@Autowired - mostra para o spring que em determinados momentos ele deverá fazer um injeção de dependências

Criando construtor
EX:
	final ParkingSpotRepository parkingSpotRepository;

	public ParkingSpotRepository(ParkingSpotRepository parkingSpotRepository){
		this.parkingSpotRepository = parkingSpotRepository;
	}

@Transactional
- Quando for métodos contrutivos ou destrutivos, vale a pena utilizar
- Caso ocorra algum problema durante o processo ele garante que não tenha dados quebrados



*Controller*
Camada que recebe as solicitações e acionar o service que vai acionar o repository.
@RestController - esteriótipo do Spring
@CrossOrigin - define as fontes de acesso
@RequestMapping - pode ser definido no método ou na classe
Na classe - quando todos os métodos forem acessados pelo mesmo caminho, pode-se fazer o mapeamento a nível de classe (servirá para todos os métodos)
@Valid - aponta quando as validações do Validation (ex: @Email, @CPF) vão ser realizadas


*Dto (Data Transfer Object)*
Validation
@NotNull - valida se é nulo ou não
@NotEmpty - valida se a string, colletion, map ou array é nulo ou vazio.
@NotBlanck - obriga que o campo seja preenchido e que não sejam apenas espaços em branco
@Size - limita máximo e mínimo de carcteres
@Email
@CPF
@CNPJ


Convertendo Dto em Classe
BeanUtils.copyProperties(parkingSpotDto, parkingSpotModel) -> primeiro valor é o que vai ser convertido, segundo valor em que vai ser convertido


