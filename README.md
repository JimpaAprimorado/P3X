----------------------P3X----------------------

Uma nova perspectiva de como interpretar matematicamente 3D.


Quem sou eu: 
	Um simples sonhador brasileiro, ao longo de minha jornada na vida jovem fui introduzido no ramo tecnologico atravez de um computador. Sempre fui fução então desde novo mesmo arriscando perder o pc mexia com coragem. O meu primeiro computador era antigo e fraco, e apesar de ter dado muito defeito conseguia resolver os problemas quase sempre. Oque me encantava era os games, passava horas e horas com jogos (liero,egobo, test-driver5 etc..) mais quando veio a internet, tudo mudou, como venho de uma família umilde numca passei fome mais passamos dificuldades, então a internet demorou para ser inserida em minha vida. No entanto muitos colegas de escola me diziam como era jogos online e como era ótimo estar conectado. Passou-se um tempo e meus pais conseguiram a internet. Era super lenta mais o suficiente para que eu conhecese world of warcraft. Um amigo na época me arrumou, e joguei, joguei muito, encantado com todo este mundo de possibilidades, vi que a internet era boa e ruim, e tinha que saber o caminho correto para não me perder. Então descidi investir o tempo nos jogos. Pois alem de muito divertidos me ajudava a passar o tempo, tudo que eu queria era chegar logo aos 18 anos de idade para tirar minha habilitação e comprar um fusca velho que era do meu avo. Passou-se muito tempo e em um periodo fiquei sem internet outra vez. Então comessei a brincar com world-map de warcraft3, e la já vinha aquela vontade de desenvolver algo. Quando a internet voltou pra min, eu já havia mudado, mesmo com o vicio de jogos havia uma força interior me dizendo e se eu melhorasse isto, e aquilo, não só como no ramo computacional, desde novo eu já estudava como funcionava o motor de um carro, eletricidade, eletronica etc... Então no ramo digital eu pesquisava aqui e ali e aos poucos fui juntando informações minimas ao ponto de conseguir baixar o blender, neste momento tudo mudou, minha internet era lenta e o wow tinha atualizado, e eu não conseguia baixar a atualização pois demorava mais de 3 dias e a internet caia no meio do download. Assim iniciei no blender, comessei a desenvolver um projeto de um jogo capaz de superar oque world of warcraft ainda não me supria. Outros jogos foram muito relevantes tambem como Dungeon Siege 2, Live For Speed, age of mitology, Mu.... Surgiu o Dragon age Origins, e tinha graficos impressionantes e meu pc rodava 5fps neste game e as vezes crachava, nesta época o pc era compartilhado com meus irmãos, um deles ousou continuar jogando este game ate queimar a placa de video, foi triste, mais isto só me deixava mais insatisfeito com a tecnologia, pois era pra ser simples, porque isto era tão dificil funcionar em computadores mais fracos? ja sendo muito superiores ao poder de um simples video game. Eu ali já percebia que tinha algo de errado, mais ignorava este instinto. Então ao passar dos anos fui ficando velho, e varias tentativas falhas de construir meu jogo. E chegamos então nos dias de hoje, tenho 31 anos. O maximo que consegui ano passado foi criar um game online bem problematico em termos de programação, kkk mais então eu tive um insight que já vinha me perseguindo de um bom tempo. e questionava Porque todas as vezes que inicio o processo de fabricação do meu game, eu paro no mesmo lugar? A algo errado comigo?. Sempre insatisfeito com o workflow para fazer personagens, a parte grafica me deixava irritado, mesmo sendo estilizado graficamente ainda era muito incomodo ter que fazer todo processo chato no 3d, e depois de muitos e muitos modelos 3d feitos, ainda tinha que fazer animações. Tudo parecia muita gambiarra. Para que o texto não fique maior doque já esta vou adiantar. Decidi então que iria criar uma engine 2d, as pinturas 2d são maravilhosas de qualquer tipo de arte que seja, porem me lembro que temos 1 defeito, a falta de profundidade real, não poderemos ter imersividade. Então estudei tecnicas que existe hoje para o 2d imergido no ambiente 3d, e vi que era gambiarra. Tudo ficou complexo demais, os calculos as formulas, uma egine como Ue3 já e super avançada, mais tambem super pesada U5 nem róda no meu pc. Agora estou propondo oque sempre me limitou, a parte grafica.
	


Este documento prova que eu inventei o p3x. Isso é nescessário para evitar que o software se torne bloqueado por alguma entitade maliciosa.

Para quem esta interessado em fazer parte da construção deste grande projeto, antes de tudo leia com atenção, use um bloco de notas ou um caderno para escrever duvidas e colaborar com ideias melhores, novas perspectivas etc.. poderemos discutir sobre isto.


AVISO importante: esta leitura pode ser muito chata, porem é importante, para que disperte em voce leitor(a) novas perspectivas, alem de ajudar a manter apenas quem realmente se interesa no assunto. não reparem em erros ortograficos isto é o de menos aqui agora.





---------------------------------RESUMO-SIMPLIFICADO------------------------------------------------------
-----------------------este é o resumo, pule para -INICIO- se quiser detalhes-------------------------------

	Especificação Inicial do Motor Visão Geral O P3X é um motor experimental baseado em unidades fundamentais chamadas ÁTOMOS, que se agrupam em MOLECULAS, que por sua vez formam VOCs, e no Mundo se acoplam em COMPOSTO. 
	O objetivo é permitir simulações realistas e também completamente fantásticas, oferecendo comportamentos físicos, materiais e de luz inéditos. 
	O motor deve ser escalável, editável em múltiplos níveis (átomo, molécula e acima) e otimizado para renderização obrigatória em 2D ao final. 
	
	Atomos Oque são atomos em p3x? são exatamente a representação de pixels. Cada atomo é 1px e isto é configuravel no MUNDO, para escalonar um obj obrigatoriamente aumentamos o tamanho do obj, adicionando mais moleculas, ou dentro de cada molecula + atomos = pixels, se o obj precisar ter um tamanho menor com a densidade superior então dizemos que o obj estará fora de escala, isto só acontece dentro da scene principal. Para que isto funcione o sistema faz decimate/maximate controlado do obj e o salva como obj ajustado, isto é nescessário devido a densidade da scene ser fixa, vale lembrar que este ajuste de escala é destrutivo, por isto ele sempre mantem o obj original em um arquivo separado, já que durante edições o usuario pode querer modificar a escala e é simples basta alterar a escala desejada e o sistema automaticamente fará um novo obj VOC ajustado usando de base o modelo3d original, para que isto não comprometa o workflow ao gerar o novo modelo (em casos de modelos super densos) o sistema usa uma tecnica que afasta o obj da camera simulando encolhimento e aproxima o obj da camera simulando expansão, assim o usuario consegue escolher qual escala se adequa antes de confirmar o novo rebuild do obj.
	
	Atomos são os menores elementos renderizáveis. Não possuem som nem propriedades complexas por padrão. Podem ser manipulados no modo de edição. São sujeitos ao KIT-MOD-PIXELS obrigatório dependendo da densidade e distância da câmera. 
	Moléculas Estruturas primárias formadas por agrupamentos de átomos. Possuem propriedades físicas, químicas e energéticas fundamentais. São a base de tudo no motor. Toda lógica de densidade, vibração, materiais e física parte primeiro das moléculas. 
	VOCs(Validação Organizada Compativel) surgem depois das moléculas. São estruturas organizadas que utilizam moléculas como blocos funcionais. Antes de entrar na scene final, obj precisa passar por um processo de compatibilidade de densidade. Pode ser necessário aplicar D-Maximate (Dimensionamento Maximate permanente) ou D-Decimate (Dimensionamento Decimate permanente) dependendo da densidade do mundo. Esse processo pode levar tempo durante esse período:
	o objeto aparece na scene deformado, mas já pode estar visível ou manipulável Assim que a compatibilidade termina, a organela é convertida em VOC.
	Um VOC indica que: 
		a densidade do objeto agora combina perfeitamente com o mundo ele está pronto para todas as operações (física, luz, render, scripts). VOCs (após compatibilidade). Garantem coerência de espaçamentos no mundo. 
	Vibrações as vibrações substituem o sistema RGB, definindo cor, comportamento energético e outras propriedades. A seleção de vibração inclui:
		Presets manuais, Curvas personalizadas, Seleção assistida por IA, capaz de sugerir vibrações esteticamente ou fisicamente interessantes. 
	
	Luz A luz é um objeto volumétrico modelável. Propriedades Gerais:
		Pode ter qualquer forma (esculpível), densidades variadas e transparência localizada.  A intensidade da luz deriva naturalmente da densidade interna. Comportamento de Propagação: Luz se movimenta conforme sua orientação. Cada átomo de luz é recriado a cada intervalo (frame ou ms), atuando como um sistema de partículas. Átomos interagem com materiais, perdendo energia até morrerem. Luz que não interage teoricamente viaja ao infinito, mas há um limite máximo de distância/vida configurável(geralmente formato da luz define fim).existe outro método, no qual Luz é tratada Estaticamente.. Modos de Luz:
			Directional Move: volume se move na direção para onde aponta. 
			Omni Expand: expande para todas direções. 
			True Expand: expande sem preencher falhas. 
			Expand Recreate: o oposto de decimate, criando novos átomos ao expandir. 
			Static Light: volume permanece estático. Modo Alternativo: Luz Vibracional A luz não se move como partículas. Ela transmite vibrações entre átomos dos objetos. Pode persistir indefinidamente. Pode transferir dados como uma "corda vibrante" entre objetos. 
	
	Câmera a câmera é um volume modelável. Possui r-decimate obrigatório: Atomos distantes são simplificados. Atomos próximos também podem ser simplificados dependendo da escala/densidade. O objetivo é evitar processar moléculas que resultarão na mesma informação final (ex.: 50 moléculas → 1 pixel). Um bom decimate é crucial para performance e para permitir aplicações diversas, como:
		Otimização global da cena. Redimensionamento da escala/espaçamento de pontos de objetos no modo de edição. 
		
	Departamentos Internos (Módulos) Render, Luz, Física / Interações, Edição universal (átomo → molécula), KIT-MOD-PIXELS, Materiais, IA Assistente, Gerenciamento de Cena Cada departamento possui comportamentos independentes mas interoperáveis. 
		
	Repositório e Feedback: O motor terá um repositório público para compartilhamento de modelos, presets, materiais, VOCs e moléculas criadas pela comunidade. O P3X deverá enviar feedback automático de problemas, defeitos e sugestões de melhoria (opcional e configurável). 
		
	Objetivo Final Criar um motor capaz de lidar com: Realismo elevado (materiais complexos, simulações físico-químicas, luz real volumétrica). Estilos artísticos alternativos (fantasia, stylized, comportamentos impossíveis). Sistemas além da realidade tradicional (vibração de luz como comunicação, matéria com propriedades inexistentes etc.). 
		
	Como a física/luz lida com buracos na malha. Sempre que física ou luz verificar colisão/incidência em uma molécula/átomo inexistente por causa do de-maximate, o sistema busca o átomo mais próximo nas redondezas. Mesmo que o buraco exista, o motor entende o objeto como "parcialmente completo". Para objetos densos, essa procura pode subir níveis (átomos → moléculas → compostos). O de-maximate terá níveis de intensidade ajustáveis. 
		
	Normal. (novo sistema substituindo peso dos átomos) cada molécula possui uma propriedade Normal (0.0 - 1.0). 0.0 = não interage, 1.0 = interação total, Isso pode servir para física, animação e bones. Em vez de perder controle removendo peso dos átomos, o usuário pode ganhar controle aumentando o número de moléculas e reduzindo átomos internos. Moleculas possuem tamanho ajustável, talvez com suporte de IA no futuro. Marcação de objetos de-maximados Todo objeto que passou pelo de-maximate recebe uma tag interna. O renderer sabe diferenciar: objetos com buracos naturais de objetos com buracos causados por compactação artificial KIT-MOD-PIXELS.

	Modificadores podem ser instalados em: objetos, câmera, mundo, compostos individuais Todos configuráveis, ativáveis/desativáveis. Existem também decimates/maximates obrigatórios do pipeline para garantir: zero duplicação de pixels, eficiência máxima do renderer, Propriedades Custom, Herdabilidade configurável. 
	usuários podem criar e compartilhar novas propriedades com o banco global. 
	
	RENDERIZAR, o ambiente realtime reduz drasticamente seu FPS. Evita conflitos com física/luz/atualizações dinâmicas. Permite gerar: imagens de altíssima resolução, vídeos comuns, videos 360, videos 3D, onde o telespectador pode se mover dentro da cena Novos Formatos Universais e Propriedades Customizadas Será desenvolvido um conjunto de novos formatos universais de objetos, aplicáveis não apenas ao P3X, mas também para mídias gerais como áudio, vídeo e modelos. 
	com o avanço do motor, uma nova perspectiva permitirá criar formatos de arquivo/media/video mais simples, poderosos e universais. O P3X poderá importar/exportar estes novos formatos. 
	Propriedades Customizadas Propriedades Customizadas vêm vazias por padrão (empty). Qualquer usuário pode criar, editar ou excluir propriedades customizadas em qualquer composto, átomo, molécula, mundo, câmera, etc. Essas propriedades permitem configurar comportamentos adicionais, parâmetros científicos, extensões criativas ou dados específicos.
	
	


-----------------------------------INICIO-----------------------------------------------
------------------------abaixo todos detalhes mais bem explicados-----------------------

Iniciei buscando enteder o basico do funcionamento do nanite do UE5 para me ajudar a ter uma ideia doque poderia fazer, eu ja estava enjuriado dos vertices, e então verifiquei que Zbrush nao o usa, apartir dai desenvolvi o sistema conceitual principal de P3X.

O processo de desenvolvimento teórico do P3X oscilou muito ate eu realmente ter bem definido o seu real funcionamento, imaginei varias possibilidades e por fim cheguei em um resultado que até então supera todo o ambiente 3D conhecido atualmente em conceito, bastando apenas transformar em realidade.

A principio iniciei conceituando como poderia representar 3D em uma tela 2D, ou seja, como gerar profundidade, sem nescecidade de vertices:

Tratando-se de 3D tudo realmente no final é renderizado em um monitor 2D. Então pensei no seguinte, vamos imaginar que ao invez de vertices, nós agora vamos usar pontos, em um ambiente 3D, estes pontos tem posição xyz, no qual determina onde ele deve estar, vamos chamar os pontos de Atomos, cada Atomo seria representado como 1 pixel real no monitor, porem depois de investir, percebi que um obj representado com pixels, se eu aproximase dele iria faltar informação, obrigando a criar uma ampliação de pixel ou um obj de escala maior que a resolução maxima do monitor utilizado. então determinei um sistema de escala, assim ao se aproximar de um obj teria mais informações, porem se eu me distanciar ainda ha problemas, mais de 1 atomo se encontram em apenas um pixel na tela, e tive que desenvolver a ideia de um KIT-MOD-PIXELS(decimate, maximate, de-maximate), isto será tratado la na frente, mais é importante ja adiantar um pouco.

  O ESPAÇO P3X É DISCRETO: Todo ponto do universo P3X existe apenas em posições da malha, nenhum ponto pode ocupar coordenada fora da malha, posição, rotação e escala de objetos precisam respeitar a malha, movimento ocorre em saltos discretos, mas com densidade suficientemente alta se torna imperceptível.
  Ou seja: O universo P3X é perfeitamente discreto, nunca contínuo. Isso é importante porque: simplifica alpha, elimina float point errors, mantém coerência perfeita entre objetos, física e renderer, permite otimizações massivas, reduz o custo geral da engine, garante, previsibilidade absoluta do sistema, É uma abordagem completamente diferente de engines convencionais.




-------------------------TECNOLOGIAS E FUNCIONALIDADES/ELEMENTOS----------------------------

----------------------------------PRESCENE-------------------------------------

	conceito: é o mundo onde fica cada obj. durante a construção de qualquer obj, voce o faz em uma scene especifica dele, isto é nescessário para que o usuario possa utilizar a densidade desejada, por ex: se quiser fazer uma maçã com muitos detalhes, incluindo partes internas, deve-se fazer o obj com densidade maxima(todos os pontos preenchidos por atomos), e tambem de tamanho/escala enorme, na qual permite obter milhoes de atomos. no entanto ao instanciar na scene principal, o obj pode ser escalonado para proporção desejada, e isto cria um decimate no obj para que ele contenha menos atomos, pois é a unica forma de encolher um obj. o mesmo vale para um obj muito pequeno, ao instanciar no mundo o obj deve crescer por ex, e isso exige maximate.



---------------------------------SCENE/MUNDO-----------------------------------------
	
	conceito: Local onde, instanciamos os nossos modelos 3D.
	
	escala: é definida pelo espaçamento entre Atomos, isto define a qualidade maxima suportada da scene, obrigando objts de diferente escala passar pelo proscesso decimate/maximate, para se adequarem a mesma densidade maxima do mundo. O espaçamento minimo real é de 1 pixel, podendo assim ser alterado para 2p 4p e assim em diante, lembrando que se a escala é maior que 1pixel, os atomos naturalmente representam mais que 1pixel, e o resultado final pode ficar pixelrizado, vantajoso para graficos estilizados, ruim para realismo.

	particulariedades: dentro do mundo, a distancia entre os atomos é uniforme e segue um quadrante grid xyz, sendo assim não permite atomos livres com flutuação(não inteiros).
	
	
	PROPRIEDADES:
		Grid-XYZ.(guarda referencia em saltos por compostos, para cada composto que contem ex:50000 átomos, ele eleva +1 em X, assim temos uma matriz menor que referencia Compostos, isto é para acelerar proscessamento interno).
	
	

----------------------------------PONTO--------------------------------------

	conceito: é a representação de uma posição no espaço 3D que pode ou não conter o Atomo.
	
	posição: a posição do ponto é fixa seguindo os parametros da SCENE.
	
	densidade: é definida por SCENE.	
	
	
--------------------------------ATOMO-----------------------------------------

	conceito: ponto no espaço 3D imaginário capaz de representar 1 pixel, futuramente para graficos estilizados pode conter formatos circulares triangulares etc... para isto logicamente os atomos serão maiores que 1 pixel.
	
	no departamento de edição do obj: voce pode arrastar átomos, excluir criar, apartir de brushs, procedural, IA etc..
	
	PROPRIEDADES:
		ID: faz referencia a sua posição dentro da molecula em que esta.(para economisar dados)
		vibração: 0.0 a 1.0 substitui RGB, em 1 unico dado de informações 0.0 a 1.0 (as casas decimais descidem a qualidade de cor), define o espectro de cor rejeitado a luz.(ex: se o espectro está para azul então atomo rejeita azul e absorve outras cores, devolvendo a cor prevalente azul, isto se atomo da luz tiver para azul).
		absorsão: 0.0 a 1.0 capacidade de subtrair da luz uma quantia de sua força, interação varia diacordo a compatibilidade de vibrações(é como se foce saturação, o resto se torna como efeito de irradiance).contabilizando cor final para pixel no renderer e colaborando com rebatimento de luz.
		reflectancia: esta em faze esperimental(pode ser removida)(é a fórma que encontrei de calcular a forma que irradiancia age sobre o mundo, se for maior a reflectancia mais concentrado fica a irradiancia sendo assim o obj parece mais liso, com brilho intenso e focal, em casos de baixa reflectancia teremos obj mais opaco, com difusão de irradiancia em uma area maior sem ponto focal, é como se foce roughnnes).
		alpha: alpha blend 2d, a camada anterior proscessa blend com camada atual.	
		custom_properts: pode ser criado aqui propriedades customizadas diacordo a nescecidade do usuario.
		

----------------------------------MOLECULA--------------------------------
	
	conceito: Conjunto de Atomos organizados por Id, possui densidade(alguns átomos faltantes) e escala(quantidade de átomos por molecula) variavel(pode ter muitos ou poucos atomos, oque ajuda na definição do obj3D).
	
	colisão: é a parte minima que contem info de colisão, com curvas seletivas, ou custom propriedades de atomos, no qual pode-se utiliza-los para influenciar o ponto que mais influencia na colisão da molecula.
	
	ossos: molecula é o proprio osso de influencia, podendo assim controlar/animar obj, seguindo mesma premissa de colisão, tambem contem curvas e opcionalmente pode utilizar atomos para influencia. (ao se mover um obj com densidade maxima, pode ocorrer de atomos se encontrarem no mesmo ponto, sendo assim renderer os calcula como 1 só, este sistema é um pouco complexo porque tambem esta relacionado ao obj permitir rasgar, ou não rasgar, ou seja que o obj se deforme sem buracos).
	
	tamanho: o tamanho minimo de uma molecula é de 8 atomos. e o tamanho maximo não existe, porem há uma regra, o escalonamento é proporcional a um grid imaginário, ex: se voce amplia uma molecula de 8 atomos em x, ela cresce adicionando 4 novos pontos na mesma direção. o formato da molecula sempre será quadrado ou retangulo, futuramente poderá existir variações de moleculas como por ex de formatos triangulares/circulares, porem inicialmente não.
	
	normal: é totalmente diferente de normal conhecida hoje. esta normal é um float 0.0 a 1.0 que determina o peso de influencia para física, colisão, animação, e serve de referencia para modificadores, por ex: maximate (Normal contem checkbox, pode ser desabilitado para objts estaticos economizando proscessamento, ja que proscessador não olha para normal se checkbox estiver desmarcado)
	
	Rigidez: Dureza da molécula, voce pode definir para animações/interações de colisão o quanto os Atomos podem se sobrepor, para dar aspecto macio.(rigidez pode ser desabilitada com checkbox desativado, eliminando proscessamento para objts estaticos).
	
	Som: atravez das propriedades da propria molecula, podemos compreender como é o material, e como se comportará com som, entretanto podemos criar com propriedades custom, respostas diferentes, para simular objts diferentes, isso é importante para desenvolver coisas fantasiosas etc...
	
	PROPRIEDADES:
		ID: Faz referencia a qual parte do VOC se encontra, no mundo XYZ.
		Normal.
		Rigidez.
		Custom-Propriedades.
			
	PROPRIEDADES-HERDADAS: pode ser escolhido a forma de herdar(média/menor/maior/IA/etc..)
		M-Vibração: média/menor/maior/IA vibração entre tdos átomos contidos.
		M-Absorsão: média/menor/maior/IA absorsão entre todos os átomos contindos.
		M-Alpha: média/menor/maior/IA alpha entre todos átomos contidos.
		M-Reflectancia: média/menor/maior/IA reflectancia entre todos átomos contidos.
		

--------------------------------VOC---------------------------------

	conceito: obj ja carregado/instanciado no Mundo, ja feito compatibilidade para mesma densidade, e reescalonado para manter tamanho original.
	
	
	PROPRIEDADES:
		Tipo.
		CorreçãoCor-RGB.
		Absorsão.
		Alpha.
		Posição-ID.(VOC armazena posição relativa a ID interno de composto)
		Rotação-XYZ.
		Escala-XYZ.
		
	EXTRAS:
		Vocs são os objts em sí ja preparados para o MUNDO. e tambem terá propriedades custom como:
		elasticidade especial, condutividade, magnetismo exótico, comportamento místico, corrupção, dissolução controlada, fragilidade, calor latente específico, brilho próprio, dano etc...
		isto ajuda muito para games, determinar física/interação entre objts. e muito mais.

		


-----------------------------------COMPOSTO----------------------------------------

	só existe no Mundo, ou seja, no modo edição de objt não existe. É um espaço quadrado contendo muitos pontos internamente, pronto para receber VOCs, pense como um particionamento do ambiente MUNDO, isto é para facilitar o trabalho de proscessamento, ja que COMPOSTO contem indereço ID no MUNDO e faz referencia a posição real/global do mundo em XYZ, cada ponto para receber VOCs é de esparçamento configurado pelo MUNDO, ou seja se é 1pixel então assim será. a forma de montagem de cada COMPOSTO, deve ser padronizada, pois os IDs devem ser coerentes com os mesmos dos objts. todos usam IDs para referenciar posição real no mundo xyz, e no renderer ou em fisica / colisão / animação o proscessamento, ids são referenciados para XYZ.(é importante resaltar que a forma de reconstrução/montagem de IDs eu sugiro que seja em espiral 3D, sendo assim todo composto/voc/molecula sera montado da mesma forma e todos referenciados com IDs, tambem há um sistema de montagens ja existente chamado Morton order, deve ser considerado).

	Update_voc: Toda vez que um VOC é modificado, animado, criado ou apagado, só atualizamos os compostos do VOC alterado no MUNDO, não precisa percorrer todos compostos que não mudaram. isso economiza muito proscessamento.



	
	PROPRIEDADES:
		Tipo.
		CorreçãoCor-RGB.
		Alpha.
		Posição-ID.(ID relativo ao Mundo, serve para facilitar computar dados)
		Rotação-XYZ.
		Escala-XYZ.
		



---------------------GRUPO---------------------------------------------
	tudo pode ser agrupado de menos Atomos. se voce agrupa algo pode renomear, pode modificar a influencia do grupo sobre outros grupos, pode linkar a outros grupos, e influencia-los mesmo a distancia.
	
	malha-rasgavel: check-box que vem por padrão desabilitado, isso faz com que as moleculas não desgrudem umas das outas, em animações e colisões, isto evita que a malha rasgue nas deformações, obrigando obj a ganhar FAKE-ATOMOS(atomos extras para simular continuidade de malha em objts que esticam).
	

------------------------------------VOLUME_OBJ------------------------------------------------
	objeto que contem alpha por definisão, ja sendo um objeto maciço.(alpha pode ser desmarcado se quiser). objeto especifico para criar agua, fumaça, fogo, geleia etc.. 
	
	
		
	PROPRIEDADES:
		Tipo.
		CorreçãoCor-RGB.
		Absorsão.
		Alpha.
		Posição-XYZ.(esta posição é relativa visual para usuario, pois internamente a posição é só ID dos Atomos.)
		Rotação-XYZ.
		Escala-XYZ.
		
	PENDENCIAS:
		Refração: avaliar oque será nescessário para termos efeito refração
		Transmisão: avaliar que é nescessário para obter efeito transmisão
		



----------------------------------BASICO_OBJ-----------------------------------
	Podemos chama-lo tambem de objeto oco, na verdade este é um objeto que por padrao vem sómente com suas faces construidas, ou seja, sua parte interna é ausente, este tipo de obj é mais leve que volume_obj, porem ha um detalhe importante, Basico_Obj pode tambem conter outras malhas internas, isto quer dizer que para modelos organicos como um ser humano, podemos ter pele, subpele, veias musculos, e tudo mais em seu interior.
	
	Alpha: vem por padrão desabilitado, porem para modelos que tem malhas internas é interesante utilizar alpha em camadas externas para visualizar interior sutilmente, por ex pele, no qual torna possivel visualizar a parte interna. lembrando que subsurface vem de graça.
	
	MOLECULAR-ESCALA: utiliza-se de IA para reescalonar tamanho das moleculas(definir quantos átomos tem em uma molecula), em casos que usuário quer ter mais controlhe sobre o obj ele pode encolher as moleculas, sem alterar o shape do modelo em questão. IA remapeia o obj completo com mais moleculas e mensos átomos internos de cada molecula, mantendo mesma densidade, mesmo formato final do modelo.(talvez pode existir um método não IA).



-----------------------------VOLUMETRICO_CAMERA--------------------------------
	
	conceito: é um obj fisico que tem densidade maxima identica a densidade definida no MUNDO. o renderer interpreta todos os Atomos da camera que ocupam espaços de outros objts. se algum atomo de algum obj estiver na mesma posição do atomo da camera, então renderer pega dados do atomo do obj e o armazena como pixel no buffer.	
	
	formato: o formato da camera define angulo de visão e fog, se ela é muito cumprinda então veremos muito distante, e para perspectiva/focal lenght podemos torna-la conica, ou retangular/quadrada para ortografica. pois no renderer os pontos que se encontram serão unidos para 1 pixel. camera tambem pode ser modelada para ter um formato inusitado.
	
	densidade reduzida: tambem pode-se aplicar um tipo de densidade diferente em partes da camera_obj, tanto para alcançar um estilo diferente de render, como para performance onde a vista distante pode ser menos densa, fazendo com que os atomos da camera fiquem esparsados, evitando calculos de merge(junsão de varios atomos para render final), ja que muitos tendem para o mesmo pixel da tela final, encurtando o proscessamento, porem pode decair a qualidade, visto que não haverá uma média de informações e somente selecionado o atomo mais proximo do obj que toca ao atomo da camera. Este efeito é quase como o decimate de renderer.(considerar possibilidade de escalar os átomos esparçados para tocar em mais atomos de objts, coletando mais informações e mergeando para 1 pixel, e garantindo assim não haver buracos entre camadas para o buffer)
	
	
	Rotação: para rotacionar basta utilizar a parte do array que ja esta selecionado como a parte do MUNDO, então movimentamos os arrays da camera, aplicando esta transformação de rotação com algumas mudanças(calculos) especificas de rotação.
	
	Movimentação: apartir de quando encontramos o bloco do array onde se localiza a camera no mundo, podemos arrastar o array seguindo os eixos desejados, e isto vale para qualquer obj.
	
	Alpha_distance: é uma opção que cria um alpha suave acumulativo do fundo para frente deixando visualmente mais suave os objts que estão longe ficam com cores menos vibrantes.
	
	
	expand_camera: é um segundo obj camera que fica em volta da volumetrica-camera, serve para calcular luz e física, colisões que não estão sendo mostradas na tela, porem luz proximas da camera ainda devem influenciar objts proximos. é uma opção que pode ser adicionada para mais realismo.
	


---------------------------------VOLUMETRICO_LUZ---------------------------------------

	conceito: é um obj fisico de densidade configuravel, geralmente maciço, com formato modelavel. Luz permite sbreposição, ou seja os átomos de luz sobrepõem atomos de outros objts, e é assim que a luz inside sobre o mundo, a cor dos objétos é definida pela somatização das vibrações dos átomos, então para que hajá visualização no ambiente 3D a luz é fundamental, ela inside em um obj e reage. A força/intensidade da luz oscila entre sua densidade e alpha, ou seja, para cada átomo que existe em luz se o alpha for fraco então a intensidade de luz é muito forte sobre objts, este alpha é contabilizado de forma diferente pelo renderer, ja que em sí ele só serve para modificar os dados dos objts. durante renderer ele pega cada ponto/atomo de luz, verifica se esta em contato com algum obj (isto funciona no macro moleculas/voc etc... antes, para performance),se algum átomo de objeto estiver em contato, contabiliza então a vibração deste átomo com a vibração do átomo da luz. então se neste caso as duas vibrações forem idênticas, o átomo não terá cor, no entanto existe um controlhe chamado Absorsão, na qual controla o nivel de absorsão do átomo, apos este acontecimento renderer joga o resultado no buffer e continua o proscesso.
	A luz é revolucionária, pois ela gera tudo facilmente por tabel, ou seja tudo vem de graça, pois a luz é uma coisa fisica no P3X, então o obj que recebe a informação de vibração do átomo da luz, tambe executa um decaimento/roubo de energia, ou seja toda particula que entra em contado com luz, absorve uma quantia de sua energia, fazendo isto temos de graça ambiente oclusion, sombras perfeitas etc...
	
	Volumetrico-luz é revolucionario assim como P3X, porque muita coisa dificil agora vem facil.
	
	mais é importante dizer que existem pendencias. Luz para que funcione corretamente deve ser movel, ou seja se for uma luz de formato redondo, deve expandir seus átomos como em uma animação, e reiniciar seu movimento rapidamente, isso é nescessário devido a precisarmos que o mesmo átomo de luz entre em contato com varios átomos do obj, assim a incidencia de luz vai decaindo sua energia durante o contato, isto é perfeito. as cores não absorvidas é que veem em nossos olhos(são contabilizadas no renderer para pixels), sabendo disto voce leitor(a) pode perguntar como o obj terá uma cor branca por ex? ja que cada átomo só tem vibração e absorsão? e se ele não absorver a vibração da luz, ele vai devolver exatamente a vibração dela, sendo assim o obj teria muitas cores, porem não ficaria branco. mais agora vem o grande detalhe, lembro a voces que P3X foi feito para trabalhar com maxima densidade, e em enorme escala, com muitos e muitos átomos, sendo assim quando renderer contabiliza os átomos de cor e os funde para 1 pixel ele contabiliza as vibrações e os transforma em RGB adequado, sendo assim conseguimos ver obj branco, desde que a cada pequeno grupo de átomos tenhamos todas vibrações, e absorsão media para minima, assim conseguimos irradiar todas as cores para renderer, que as somatiza e interpreta branco. este é o melhor sistema que eu consegui inventar ate agora em volumetrico-luz e isto é inédito na historia da computação.
	
	os átomos do obj volumetrico-luz são tratados como emissor, porem eles não são visiveis, somente em contato com outros objts, então se ouver um volume de fumaça tambem receberá influencia de luz e a tornara visivel.
	
	devemos aperfeiçoar este projeto, pois penso muito em tornar a luz em algo estático, e mantendo sua funcionalidade, porem quando pensamos em luz estática não conseguimos sombras, ja que os átomos de luz apenas entram em contato com 1 átomo do objt, não perdendo assim sua energia.
	
	há outras formas de atuar com a luz, no caso os objts tambem tem o poder de devolver parte da luz, no caso isto acontece naturalmente que é a absorsão sendo pouca, neste caso então a insidencia de luz é pequena sobre o átomo do objt, e isso pode indicar 2 coisas, que o objt recebe toda luz e absorve pouca energia e devolve para o meio muita energia, e/ou "suga" pouca energia do átomo da luz. isto nos da mais uma forma de luz atuar sobre o mundo.
	
	os objts podem tambem executar rebatimento de luz, se imaginarmos que a energia capturada pela lampada entra no átomo do obj, ele pode devolver parte da energia, porem com vibração alterada baseada na própria vibração, assim ele devolve para o meio uma luz diferente da recebida, se conseguirmos fazer com que esta nova informação de luz entre em contato com os átomos proximos, incluindo outros objetos, teremos rebatimento de luz perfeito, porem a unica solução facilmente perceptivel que tive foi que para isto deveriamos gerar átomos que se movem em direção aleatória que se chocam com atomos proximos alterando suas informações. porem isto é custoso para processamento, devemos encontrar melhorias para isto.
	
	Inicialmente antes de pensar em luz como particulas emissivas, eu imaginei literalmente que a luz seria um obj menos denso e ao invez de se mover em alguma direção(por ex: se luz for esferica os atomos nascem do centro e se movem para fóra expandindo), luz poderia simplesmente conter menos átomos, e cada átomo circulace em uma orbita pequena, isso manteria a funcionalidade total/parcial de sombras, AO, e tambem permitiria melhor proscessamento, alem de conseguirmos afinal um sistema de rebatimento de luz.
	
	Luz pode alterar a vibração de seus átomos em realtime, ex: se tivermos um obj com todos átomos de vibração para azul, e nossa luz é relativamente branca, então sabemos que o obj será renderizado como amarelo, pois ele absorverá todo espectro auzul da luz, entretanto podemos tambem imaginar que volumetrico-luz, pode interagir com o obj amarelo, isso significa que uma parte do emissor luz com vibração para azul se perdeu no obj amarelo, sendo assim luz pode ficar mais amarela e/ou mais fraca assim se ajustando em vibração e alpha, e se introduzirmos outro obj ele sera influenciado por isto. portanto, luz tambem altera seu espectro de cor e alpha, diacordo a absorção do obj que interage.(isto ainda é conceito, devemos testar e ver os resultados e avaliar se isto é valido).
	

	PROPRIEDADES:
		ID: define posição que esta em Composto.
		Tipo: Estático(pode conter animação), Particula, Vibrar, Custom...
			se escolhido Particula:
				Expandir: true-expand(expande o volume mantendo seus átomos maximos, reduzindo assim a densidade da luz), recriar-expand(expande mantendo a densidade, criando novos átomos de luz para manter densidade, pode ser integrado com IA.), encolher(do shape para o pivot, eliminando átomos, ou os sobrepondo). etc..
				Tempo: quantidade de particulas criadas, ex: 1ms, 2ms....(a luz em particulas se acaba ao colidir com objts, então ela não precisa de tempo de vida.
				Distancia-maxima: shape3D, 2ms, ifinito(até morrer as particulas por falta de energia perdidas por contato a objts).
			se escolhido Estático:
				Escala-Rebatimento: tamanho do brush que contabiliza rebatimento de luz.
				etc..


	ANIMAÇÔES:
		mesmo em volumetrico-luz estaticos, o usuário pode criar animações de átomos e moleculas utilizando:
			animação-manual: usuário anima frame a frame com interpolação etc..
			animação-procedural: utiliza ruidos e calculos matemáticos / influencias físicas para gerar animação.
			animação-IA: animação gerada frame a frame com IA.(usuário pode ajustar animação manualmente se quiser).
		Salva-estados: animação salva estados anteriores, caso usuário "estrague" uma animação anterior pode ser recuperada.
	
	EFEITOS:
		IRRADIANCIA: efeito calsado pela interação de objetos, que recebem luz e devolvem uma parte da luz absorvida para o meio, irradiancia deve ser bem estudada, podemos determinar que será feita por samples, porem este método seria pesado. talvez haja algumas outas possibilidades melhores e mais simples.
			irradiancia-por-absorção: seria a reemissão de luz para a propria lampada, atomo de obj recebe luz, absorve, e devolve o que não absorveu para luz, porem com adicional interferencia, não havendo assim nescecidade de samples, pois depois de irradiar obj para de interagir, e só volta na proxima renderer.(devemos estudar melhor isto)
	
	
	
	INFORMAÇÔES IMPORTANTES:
		ALPHA: define a intensidade/força da luz, 0.0 a 1.0 com varias casas decimais para mais precisão. quanto menor alpha menos insidencia/força. a cada contato com atomos de objts, á um decaimento, baseádo na absorsão do objt.
		
		ABSORSÃO: luz tambem possui absorsão, isto é devido a nescecidade do rebatimento de luz, na qual luz recebe informação dos átomos de objts, e repassa para outros átomos, quando se move. luz absorve o rebatimento de luz que átomos enviam como irradiance.
		
		VIBRAÇÂO: cada átomo de luz contem vibração 0.0 a 1.0, vibração, é só imaginar todas as cores visiveis que estam representadas entre 0.0 a 1.0, com varias casas decimais para maior precisão, vibração dos átomos de luz podem ser alteradas em realtime, por interferencia de objts.
		
		LUZ pode ser calculada antes ou depois de r-decimate, o usuário pode escolher via config, isso é nescessário, pois para computadores fracos é interesante que ocorra a redução consideravel de átomos na scene para depois calcular luz, sendo assim podemos ter um ganho de performance muito grande, ja que no final dos calculos de r-decimate restarão apenas pixels compativeis com a tela do usuário, em comparação com muitos milhoes de átomos que existem no mundo antes de r-decimate, porem é importante que exista a possibilidade de calcular luz antes, para quem precisa de alta fidelidade visual, para ambientes cinematograficos etc... 
		
		DE-MAXIMATE pode ser habilitado para que luz seja contabilizada utilizando este método nos objetos, isto reduz o proscessamento, porem tambem compromete a qualidade de iluminação e cor.
	
		
	
	COJITAR/AVERIGUAR:
		Luz orbital
		Luz estática(talvez, computacionalmente, os átomos passam dados entre sí, permitindo decaimento de energia, rebatimentos etc.. não precisando ser movel realmente)
		Luz particulas emit
		Comportamentos como rebatimento, reflexo etc..
		Amostras de átomos externos.(isto pode facilitar o proscessamento, e permitir luz estatica, dispersão física de volumes)
		Adição de Roughnnes, como propriedade de átomos, para definição de superficies lizas/asperas(roughness controla quanto a luz se espalha para os pixels vizinhos. se roughness alto espalha muito, gerando uma especie de blur. se roughness for baixo, mantemos a luz concentrada.)(este sistema dependeria de Amostras de átomos externos visinhos)
		
		


--------------------------RENDERER------------------------------

	O renderer separa os Atomos em contato com a camera e os renderiza do fundo para frente, isso é facil devido a camera ser um obj, renderer funciona em tempo-real, então tudo que tem que acontecer dentro de P3X acontece sempre, sem precisar apertar start.

	info base: renderer depende totalmente da camera, baseado em seu formato e comprimento, renderer contem um framebuffer2D que armazena de camadas em camadas sobrepondo e recalculando os atomos nescessários(alpha,vibração,difusao etc...) ao termino ele pula para proximo passo.
	
	permite configurações avançadas de renderização como ordenação de prioridades em FraPriTe etc...
		
	TECNOLOGIAS ADICIONAIS NESCESSÁRIAS:
		R-Decimate
		R-Maximate
		FraPriTe
		
------------------------RENDERIZAR-----------------------------------------
	O renderizar é o módo que voce tira uma "fóto" ou faz um "video" e o armazena. este método é nescessário para extrair o maximo grafico possivel. quando acionádo ele força o renderer a 1FPS 0.1FPS etc.. então o renderer trabalha super lento em termos de imagens, porem o proscessamento interno pode trabalhar com muito mais precisão e riquesa de detalhes. 
	
	OPÇÔES:
		Gravar	: grava o video no formato desejado da forma desejada na resolução desejada.
		Imagem	: grava imagem super definida após a contabilização e proscessamento super detalhado, voce pode definir o maximo de qualidade, via configurações.
		
	CONFIGURAÇÔES-RENDERIZAR:
		aplicar upscale no final é possivel com IA.
		Imagem:
			3Dimagem, 2DImagem, GIF-3Dimagem....
			numero de samples, resolução(dobrar,triplicar,quadruplicar etc..), desabilitar KIT-MOD-PIXELS, etc..
		Gravar:
			video, 3Dvideo(video que usuário pode assistir se movendo no mundo),360video, resolução(1x,2x,4x,8x etc..), desabilitar KIT-MOD-PIXELS, etc..
			 

	
			
----------------------------DECIMATE--------------------------------------KIT-MOD-PIXELS
	
		d-decimate: é feito para VOC ou seja, para normalizar o espaçamento entre o obj e o mundo.(d-decimate é obrigatorio e automático) só acontece quando obj foi feito com ex: espaçamento de 1pixel entre pontos, e MUNDO foi configurado para 4pixels(distancia entre pontos então seria 400% da escala real, ou melhor dizendo cada atomo ocuparia 4pixels), e para manter a escala do obj ele se encolhe no mundo ex: obj foi feito com 1pixel de espaçamento em Prescene e sua escala era de 2m2m2m(2 metros), perdendo atomos/moleculas. este processo é destrutivo, porem salva automático um novo obj, mantendo o obj original intacto:
			interpolação: exclui átomos proximos, mantendo obj smooth em cores e shape.
			pixelrização: remove atomos do obj, criando forte quebra/descontinuação de propriedades como cor,alpha etc.. isto pode deixar obj mais quadriculado, cores podem ficar mais pixeladas, colisão/fisica/animação ficam mais "quadradas".
			IA: recria o obj por completo utilizando como parametros os atomos centrais de cada merge como parametro tentando manter o fluxo natural do obj.
		
		r-decimate: é o decimate no renderer nescessário para interpolar atomos proximos que convergem em 1 pixel na tela.(r-decimate é obrigatorio e autmatico, em uma tela 2D seria desperdicio de proscessamento calcular em profundidade todos os átomos, ja que no final muitos convergem para apenas 1 pixel.). isto acontece no renderer e varia diacordo a distancia de visão, é inteiramente ligado a camera, ja que nescecita dela como parametro de quais atomos estão mais distantes. possui parametros de configurações na qual pode-se selecionar a forma de merge desejada:
			media: seleciona os atomos e tira média de todas propriedades gerando um atomo/pixel que os represente como mediano.
			aleatório: seleciona dos atomos que estão para 1px aleatoriamente, para o buffer. pode tornar imagem mais ruidósa/contrastante em longa distancia de visão.
			central: se ouver um atomo central dentre muitos o seleciona para o buffer, em casos de haver poucos atomos para 1px como 2 ou 3 atomos ele seleciona por padrão aleatoriamente um deles.(isso é devido a nescecidade de rapidez de proscessamento).
			normal: baseado na normal de cada átomo o que possui maior numeração entra no buffer, se for mais de 2 no mesmo quadrante é aleatoriamente selecionado um deles.
			custom-pro: usuario cria custom prop e adiciona-o como base para r-decimate.
		
		s-decimate: é acionavel, principalmente para jogos, na qual não só o renderer merge os atomos, como tambem a scene inteira baseando na distancia da camera, isto acelera o r-decimate, alem de reduzir consideravelmente atomos contidos na scene, oque agiliza os testes de fisica, animação e colisao).(acionado por check box), na verdade ele salta atomos os desconsiderando para tudo(fisica,color etc..), buracos no obj não aparecer porque distancia da camera indica o nivel maximo permitido para decimar sem comprometer a continuidade de malha. pode atrapalhar fisica, pois é dinamico. pode ser desmarcado partes a desconsiderar como física etc... com checkbox.
		
		merge: é um modificador destrutivo que usuário pode aplicar no modelo 3D para encolhe-lo(reduzir detalhes) é feito backup automatico, e contem formas de ser aplicado.
			aleatorio-merge: pega dos atomos proximos 1 aleatorio e remove os outros encolhendo o obj mantendo densidade maxima.
			molecular-merge: seleciona molecula com maior peso e remove as proximas para encolher obj.
			IA-merge: IA recria o modelo por completo avaliando todos os atomos com suas propriedades e tentando encolher o obj mantendo seu aspecto e propriedades.
			
		reduce: sistema de escalonamento de objeto, para que seja possivel que obj possa encolher é nescessário uma forma de mergear atomos, é funcinal quando nescessário animação/fisica etc.. é feito um sistema simples que merge os atomos os permitindo posicionar no mesmo ponto, este recurso pode consumir muita ram se obj for muito grande.não é perfeito pode ser repensado.(cogitar possibilidade de reduce jogar alguns átomos para dentro da malha para esconde-los e assim encolher rapidamente o modelo, sem perda, digo considerar porque talvez não seja uma boa ideia devido a objts muito grandes exigirem muito proscessamento).(outra ideia é que podemos escalonar o obj mantendo camera parada e o sistema joga obj para o fundo do mundo, para dar sensação de encolhimento, assim o usuário pode selecionar encolhimento desejado, apos comfirmar obj passa por d-decimate novamente gerando assim novo obj VOC, na escala desejada).
		
		
		EXEMPLOS:
		1- em um mundo se tivermos um cubo 200x200y200z teremos problemas se movermos a camera de forma a que o vemos menor que seu tamanho real, ou seja se  nossa camera tiver formato de perspectiva, e afastamos do obj, teriamos de ve-lo muito menor que 200pixels, a camera por ser volumetrica em formato de cone deforma naturalmente a imagem quanto mais distante estiver, comprimindo os pixels, isto obriga ao renderer descidir quais átomos vão ficar de fora e quais vão ser representados como pixel no buffer. este proscesso se chama r-decimate, no qual o renderer escolhe o atomo a ser representado em pixel e ignora os demais, lembrando que há varias formas de ser tratado, e isso vai da escolha do usuário, porem vem por padrão o metodo central.(R-Decimate, é obrigatorio pois não ha como representar 50 átomos em 1 pixel, logo deve-se haver uma forma de descidir quem vai e quem fica). Vale dizer que para maior performance, pode-se utilizar a camera com densidade variada diacordo a distancia, isto faz com que os pontos de contato da camera sejão mais esparçados em longas distancias, encurtanto os átomos selecionados para o proscesso de r-decimate. em camera, se densidade for minima por distancia, então r-decimate atuara minimamente. a diferença é que a camera ja seleciona as informações dos átomos e ja as envia diréto para buffer, porem se camera tem maxima densidade, o r-decimate precisa coletar de todos atomos seus dados e tratalos para 1 pixel, isto cria mais proscessamento, apesar de representar com mais fidelidade os objts do mundo.
			
----------------------------MAXIMATE----------------------------------------KIT-MOD-PIXELS

		d-maximate: é feito para VOC, normaliza o espaçamento do obj Prescene com o mundo(d-maximate é obrigatorio e automático), só é aplicado se obj tiver espaçamento de pontos maior que o MUNDO, ex: mundo tem espaçamento de 4pixels, e obj foi feito com espaçamento 8pixels, logo para manter escala do obj prescisamos cresce-lo. d-maximate é destrutivo e salva obj na pasta mantendo original intacto, ele aumenta o numero de atomos/moleculas do obj. (no modo de importação para o mundo voce pode selecionar a forma de d-maximate agir:
			interpolação: cria novos átomos com propriedades proximas, mantendo obj smooth em cores e shape.
			pixelrização: cria atomos para preencher obj, mantendo as propriedades identicas dos atomos ja existentes, isto pode deixar obj mais quadriculado, cores podem ficar mais pixeladas, colisão/fisica/animação ficam mais quadradas.
			IA: recria atomos de preenchimento tentando manter o fluxo natural do obj.
		
		r-maximate: é maximate do renderer nescessário para aproximação de objts, em mundos de espaçamentos muito maiores que 1pixel e/ou objts muito pequenos, ao se aproximar de um obj não há mais informação de atomos para cobrir os pixels da tela, o obj sumiria ou ficaria vazado, ou temos que escalonar os pixels representados pelos atomos.(é opcional, vem por padrão desativado, pois é recomendado para realismo que se mantenha uma escala de objts maior que os pixels da tela alvo, pelomenos 1.1 vezes maior para evitar bugs visuais, ex: seu monitor é 2k então faça seu menor obj do mundo com 2k2 de atomos como base.). tambem pode ser implementado sistema de interpolação trilinear para tornar mais smooth os novos pixels gerados por r-maximate em casos de objts pequenos/poucos detalhes, ou usar configurações como Fatiar(expande objeto deixando buracos por manter a densidade original sem alterar os átomos somente s separando ums dos outros), Preservar(expande objeto preservando sua estrutura apenas representando átomos com mais pixels(deixa objt pixelado)).
		
		expand: é um modificador destrutivo que usuário pode aplicar no modelo 3D para escalona-lo(mais detalhes) é feito um backup do obj automaticamente:
			fixed-expand: eleva quantidade de atomos/moleculas no obj duplicando atomos e mantendo propriedades identicas.
			blend-expand: a cada novo átomo adicionado é coletado a média das propriedades de atomos proximos elevando obj em forma mais smooth.
			IA-expand: IA cria novos atomos/moleculas de forma inteligente, para dar mais detalhes ao obj sem editar os atomos ja existentes.(pode conter opção de regenerar por completo).
			
		elevate: contrario de reduce, sistema de escalonamento de obj em realtime, obj pode facilmente esparçar os átomos e os configura para que representem + pixels por atomos, evitando buracos na malha. isto não é perfeito pois pode deixar obj pixelrizado, pode ser repensado. (outra ideia é que podemos escalonar o obj mantendo camera parada e o sistema joga obj proximo a tela(parafrente), para dar sensação de expansão, assim o usuário pode selecionar dimensão desejada, apos comfirmar obj passa por d-maximate novamente gerando assim novo obj VOC, na escala desejada).
		
		
		EXEMPLOS:
		1- imaginamos que há um cubo 2m2m2m no mundo, e nossa camera renderiza para tela 400x400y, se estabelecermos que 1cm é = 1pixel, e nosso mundo esta configurado para escala de 1pixel, então teremos a representação de 200pixels para 2 metros. podemos deduzir que ao renderizar veremos o cubo com 200 pixels se a camera estiver a 400 atomos/pixels de distancia Z sem rotação, ainda vale resaltar que estamos utilizando uma camera ortografica. ok por hora tudo funciona, porem se aproximarmos a camera para 200 atomos/pixels do centro do mundo de nossa tela continua 400x400y deveriamos ver o obj completo na tela, e isto não ocorre sem maximate. O cubo deveria conter mais pixels para ocupar totalmente a tela 400x400y, sendo assim não veremos o obj, ou seja ele vai ser ocluido apos ter sua dimensão maxima, e veriamos o ultimo pedaço de traz do cubo se estivermos com a camera em 200 atomos. porem se a camera estiver em 199pixels, o obj sumira totalmente. para que isto não aconteça é nescessario um sistema de rasterização no qual chamamos de r-maximate, voce leitor poderia dizer que poderia simplesmente eliminar r-maximate, e escalonar o obj com expand ou elevate, no entanto para objts minusculos se a camera tentar se aproximar mais doque seu tamanho em pixels, o obj sumirá da tela impedindo observar mais de perto, mesmo com poucos detalhes. então é super nescessário existir um sistema na qual represente pequenos objts os escalonando no renderer apartir de quando estamos mais proximos em pixels doque o obj pode fornecer. esta opção pode ser desativada caso o usuário desenvolva todos seus objts com escalas maiores que um monitor convencional, assim impedindo este efeito de culling. vale resaltar que a principio imaginamos que o obj ficaria vazado em partes se aproximado, porem isto não ocorre ja que pela camera todos os pixels são ocupaveis por atomos.
		
		
		
	
-----------------------------------DE-MAXIMATE-------------------------------------KIT-MOD-PIXELS

		Conceito: atua na redução consideravel de densidade de objts, mantendo seu shape, e escala. é usado principalmente para objts distantes da camera, e tambem em todo o MUNDO, em termos de física,colisão,animação etc..(coisas que não fazem parte principal do visual em sí). trazendo mais economia de dados, e menos consumo de proscessamento e ram. de-maximate é um modificador ele precisa estar adicionado no obj para funcionar, voce pode selecionar muitos objts e adicionar em todos ao mesmo tempo.
		
		SALTOS: usado apenas para calculos de física e colisão, remove/ignora átomos/moleculas no momento de calcular física/colisão/simulação de agua/fumaça/fogo/luz/etc.., porem mantem o aspecto do obj intáquito. tambem possui um check-box extra para ativar a funcionalidade, possibilitando que computadores fracos consigam manter o funcionamento mesmo em MUNDOS muito densos e grandes. para que reduza erros de calculos neste caso física/outros devem verificar em um raio maior sobre os átomos, pois sabendo que alguns átomos não serão vistos pelo proscessamento ja que obj possui baixa densidade, logo deve procurar ao redor, e o primeiro átomo proximo encontrado deve servir como base para aplicar o proscessamento).
		
		SEM-SALTOS: Pode funcionar de forma que reduza consideravelmente a densidade do obj e escalone os pixels dos átomos para manter a mesma escala sem buracos, aplica física(física dentre outros devem executar a contabilização por pixels expandidos, ou seja se obj sofre de-maximate, ele tem buracos/falta de átomos, e física/outros deve saber lidar com isto). etc.. calcula.. e depois remonta o estado original tentando manter as deformações obtidas nos calculos. Objetos estáticos sem animação ou deformação podem sofrer de-maximate ainda mais forte, ja que não é nescessário muito proscessamento, nestes casos é interesante que renderer simplesmente salte átomos, os ignorando por completo, e os que são contabilizados ganham uma representação maior de tamanho.
			Reduz a densidade atômica/molecular (Decimate)
			Executa a física / luz / deformações / interação
			Reconstrói a densidade com Maximate usando diversos métodos opcionais
			tem sua principal atuação em: agua, fumaça, luz física via amostragem, tecidos macios, cabelos, simulações de vento, deformações temporais, bones avançados...
		SALTOS-RECRIADO: recria modelo original com baixicima desncidade, agrupa varios átomos, contabiliza suas propriedades e posição, e cria um novo átomo médio, excluindo os outros. este método de de-maximate age como um sistema de LOD, e pode ser precomputado, salvo em HD. no entanto para fisicas de tempo real pode gerar erros ja que obj em LOD pode trocar no momento de colisão. (deve ser mais elaborado).
		
		de-maximate tem:
			niveis de intensidade ajustaveis, 1/2/3/4....
			checkbox de ativação.(permite ativar somente em objts desejados).
			
		
		
		
		
	
	
-------------------------------------FRAPRITE-----------------------------------------------------
	Fra(fragmento)Pri(prioritario)te(temporal).
	
	é o responsavel por particionar o frame por prioridades, automatizar ajustes de tempo para manter render final na frequencia em hz proporcional ao monitor, gerenciamento temporal inteligente ajustavel por prioridades etc....
		
	Conceito: quando se trata de renderer, pensamos em apresentar um preparado de pixels na tela. busquei antes de tudo compreender o básico de um monitor, e percebi que não podemos enviar fracionados de dados, a principio queria desenvolver uma tecnica de enviar ao monitor somente os pixels que foram modificados, reduzindo assim o tamanho de dados, mais percebi que não podemos fazer isto, cheguei a cogitar possibilidade de pelomenos no buffer antes de enviar a tela fazermos isto, mais desanimei. então continuei avaliando o funcionamento.
	sabemos que 60hz = 60FPS. sendo assim eu pensei, se um monitor tem o limite maximo de 60FPS por qual motivo queremos alcançar 200 300 FPS?. Burrice, burrice total. então percebi que há como otmizar-mos o sistema de renderer. nós não precisamos tentar renderizar mais frames doque o monitor suporta, pois sera jogado no lixo, sendo assim desenvolvi FraPriTe.
	renderizamos o buffer, o monitor pega isto e joga na tela. então enquanto ainda não passou o tempo nescessário para a proxima atualização temos tempo para fazer outras coisas, então neste intervalo de tempo ao invez de continuar tentando renderizar oque será desperdicio, podemos gastar este intervalo de tempo para física, light, e precarregamento. e como tudo é bem previsivel podemos criar um script de compensação que diacordo ao peso da scene, podemos determinar aproximadamente quando devemos iniciar o processo de renderização para o proximo buffer, no qual a tela realmente vai requerer. assim ao invez de mandarmos renderizar o tempo todo e ficar calculando tudo de uma vez antes do render. podemos inicialmente calcular o nescessário e enviar ao buffer -> tela abre e lê, porem a tela vai demorar pra pedir novo buffer, então ao invez de ficar renderizando dinovo e atualizando buffer, paramos e calculamos outras coisas, dai quando estiver proximo do request do monitor renderizamos para o buffer dinovo. e para que isto não crie gargalos em pcs fracos, como o meu, podemos determinar um intervalo regulavel, ou inicialmente 1/2 do intervalo. ou seja metade do intervalo entre frames, dedicado para calculos, e metade dedicado para renderer final para buffer. e diacordo a debugs e avaliações podemos criar proporções diferentes ou regular ate mesmo automaticamente pelo script de compensação, podendo chegar ate 90% para calculos e os 10% do intervalo de tempo por frame para renderer. e isso torna ainda mais potente, principalmente se decairmos ainda mais o fps para 60 ou 50.
	assim se decairmos o fps ganharemos ainda mais tempo para calculos avançados, isso é bom d+, a média de um render por frame é de 8ms então temos de sobra 8ms ja que para 60fps a média é de 16.66ms, no entanto com FraPriTe, teremos dos 16.66ms muito mais tempo para proscessamento, ja que o renderer em sí que carregará o buffer e enviará para tela sera simples. os calculos de fisica colisao e iluminação vão precisar de mais tempo doque o renderer.
	podemos tambem particionar ainda mais o intervalo de tempo do monitor, dedicando por ordem de prioridades, como física n% colisão n% luz n% animações n% e renderer n% etc... e podemos controlar a ordem de processos tambem, isso da liberdade para os usuários e pode ser opcionalmente controlado automaticamente dinamicamente.
	
	haverá um regulador interno que define passos não prioritarios, e em caso de peso do sistema pode adiar para o proximo frame calculos secundários, alem disto tambem pode controlar o FPS, reduzindo minimamente para corrigir o peso da Scene. da mesma forma pode antecipar calculos do proximo frame, em casos de proscessamento livre, e ainda avisar usuário que pode adicionar mais qualidade na Scene por estar leve, ou avisar indicando onde pesa, para ajustes. O sistema alonga o tempo entre frames, diminui o frame rate gradualmente, dá mais tempo real para cálculos complexos, mantém a qualidade quase inalterada, evita quedas bruscas percebidas, mantém a jogabilidade/usabilidade mais fluida possível.
	
	Precarregamento de objts, e descarregamento.(para mundos gigantes, FraPriTe adia o carregamento de modelos distantes da camera para proximo frame em caso de peso do sistema e acelera o carregamento em caso de sistema leve).
	
	
	NPU: FraPriTe pode utilizar do proscessador IA para prever futuros proscessos e ja os calcular, alem de prever pesos por calculos muito densos e ja aliviar a carga de oturas formas, impedindo queda abrupta de FPS. tambem usa NPU para reconstituir pixelização causada por KIT-MOD-PIXELS dinâmicos.
	
	
	COORDENAÇÂO:
		Controlar decimate dinâmico por prioridade
		Aplicar Maximate de forma adaptativa
		Usar De-Maximate para economizar tempo
		Controlar a queda de framerate com amortecimento temporal
		Distribui orçamento de tempo ao longo de vários frames
		Faz escalonamento temporal inteligente.



----------------------------------COLISAO---------------------------------------------------------

	Conceito: Utiliza-se de moleculas para demarcar colisão, para quem quer mais precisão e detalhes, pode reduzir o tamanho da molecula que conterá menos atomos, assim poderá ter controlhe total sobre a colisão. a forma que moleculas se movem, para influenciar outras pode existir um tipo de curva que selecionamos, ou como um brush forte ao centro e suave nas bordas. tudo isto pode ser pensado.
	
	Atomico-Colisor: Para objetos(todos objetos, luz,volume,basico,etc..) volumetricos por ex, como geleia, agua, fumaça, fogo, lava etc.. todos átomos devem ser influenciados. esta opção ativa esta possibilidade, pois vem por padrão desabilitada para economia de proscessamento.
	
	Normal: Por questões de otimização objetos não tem Atomos para animação, animações para personagens etc, são feitos em moleculas, cada molecula possui esta propriedade, que define a influencia recebida pela movimentação/animação, normal é uma propriedade 0.0 a 1.0
		ex: podemos animar objetos salvando a posição de deslocamento das moleculas, personagens de alticima qualidade podem ser fabricados da seguinte forma: voce modela um osso dentro do personagem, ele contem átomos e moleculas, estas moleculas do osso voce as trava todas com rigidez 1.0, assim voce tem um osso rigido, e seleciona as moleculas para um grupo, os nomea como osso-1, determina para cada molecula do grupo normal = 1.0(isso indica que se voce mover um pedaço da molecula do osso-1 as outras seguirão de forma identica, mantendo osso rigido, se colocase normal=0.0 nehuma molecula seguiria a selecionada, se voce marcar 0.1 em todas e deixar a do centro como 1.0 então ao mover pelo grupo a molecula 1.0 é o pivot, e o resto seguira suavemente, sendo assim o osso deformará e não sera rigido), apartir disso interliga o grupo osso-1 com outras camadas superficiais do personagem as linkando com outros grupos e pondo sua influencia de 0.0 a 1.0, e faz animação apenas movendo o osso, ele move por curvas de influencia outras moleculas externas criando animação em realtime. no final voce pode dar bake-animação, e não precisando de precomputar a animação em realtime. para animações mais realistas e interativas voce pode utilizar com proscessamento realtime, apesar de consumir mais, voce consegue um resultado muito bom.
	
	Colisão e animação estam inteiramente ligadas, pois assim não prescisamos usar 2 propriedades, para representar a mesma coisa. 
	
	REDUCE-COLISOR: utiliza a Normal de moleculas para definir a interação entre objts/moleculas, para economizar proscessamento, forçando que proscessamento ignore moleculas de Normal 0.0.
	
	Colisão faz Atomos darem saltos, empurrando uns aos outros para o proximo ponto do MUNDO, alem disso tem a propriedade rigidez que define o quanto os átomos podem se sobrepor, isso define o quanto obj é duro ou macio, se for muito duro os átomos obrigatoriamente saltam para proximo ponto, porem obriga o proximo atomo tambem a saltar e assim por diante, em casos macios átomos podem sobrepor e o obj se encolhe como uma geleia, no entanto seu formato real ainda esta preservado, se a colisão é proxima da camera então os dados estão na memoria ram, se obj esta muito longe os dados estão no HD.(Rigidez é propriedade de molécula apesar de influenciar dirétamente nos átomos). 
	
	Curvas de ação existem para atuar na forma de interagir com os átomos.
	
	para objetos enormes com milhoes de átomos executar proscessos de colisão/animação pode ser muito pesado, então podemos transformar os grupos atuadores invisiveis e com menos densidade(átomos falhados, não existentes em todos os pontos, sómente alguns átomos de influencia), e utilizarmos de-maximate.
	
	podemos tambem dar opções para que a fisica e colisão só aconteção no campo de visão, ou então no mundo todo, isto é bom para setagem de nicho : é game-fisica só na visão, -é cientifico ou cinematografico -> fisica e colisão no mundo todo. 




-------------------------------------ANIMAÇÂO---------------------------------------------------
	Durante animação existem tecnicas que podem ser implementadas. uma delas é que se voce quiser animar um obj que se esticará muito, para manter muitos detalhes, pode construir o obj com varias camadas internas, estas camadas internas se deslocam para fora diacordo a deformação, impedindo a nescecidade de FAKE-ATOMOS, e deixando mais realistica a animação, este modificador se chama INTRA-EXPANDIR.
	
	PRESERVE-ANIMAÇÂO: isto é nescessário caso obj receba modificações drasticas na qual pode comprometer a animação feita anteriormente, então esta funcionalidade tenta proteger os dados de animações e se adequar ao novo estado do obj, evitando assim que usuário tenha que refazer tudo, e somente deverá fazer alguns ajustes. (esta funcionalidade tenta ajustar preservando os grupos e suas posições relatias). posteriormente podemos adicionar auxilio por IA.



-------------------------------------SONORIZAÇÂO-----------------------------------------------------
	Sons em P3X são com certeza muito melhores, pois podemos adicionar caracteristicas especificas para cada obj, e como o material físico deles reage, o som pode ser algo físico, pode emitir ondas de átomos que se chocam com objts, alem da espacialidade, ambientes influenciam dirétamente no som, podemos criar efeitos reverb, delay, naturalmente, apenas configurando o comportamento dos objts/materiais, atravez de suas propriedades.
	Paredes podem absorver e refletir som, podemos criar propriedades custom para alcançar objetivos diversos.


-----------------------------------MODIFICADORES------------------------------------

	conceito: podem ser instalados dentro de tudo, átomos, moleculas, voc, composto, MUNDO, CAMERA-MUNDO(a camera do editor), outras cameras(em caso de game).
	
	servem para atuar nos objts alterando suas propriedades, animações procedurais, configurações de renderer, física, ajudando em esculpt e muito mais.
	muitas coisas dependem de modificadores, permitindo configurações diversas para quem busca performance ou qualidade, ter controlhe sobre muita coisa é ótimo.
	alguns modificadores são obrigatorios como r-decimate, porem aceitam configurações, alguns modificadores podem controlar o renderer.
	IA é contabilizada como modificadora em objts, então voce pode adicionar um modificador IA e escrever ou gravar um audio solicitando oque deseja.
	
	Ubins: modificador Ubins adiciona um ou mais ubins dentro do elemento desejado, assim permitindo que ele tenha respostas esperadas pelo usuário, permitindo criação de jogos, automatização etc...
	
	Upscale-IA-camera: modificador que aplica na camera um upscale de pixels, tornando mais leve o proscessamento, voce pode trabalhar com ate 1/4 da resolução final, e IA reconstroi no final do buffer pixels intermediarios(FraPriTe, permite mais facilidade/agilidade neste proscesso enviando buffer ja completo para outro proscessador => NPU).
	
---------------------------------------PLAY-UBINs-------------------------------------------

	A tecnologia PlayUbins permite programar ações especificas para cada coisa em P3X, voce pode adicionar um Ubin dentro de qualquer coisa, desde átomos ate o MUNDO.
	

--------------------------------------IMPORTAÇÂO/EXPORTAÇÂO-----------------------------
	Este departamento é responsavel por guardar objts construidos dentro de P3X no HD. ele salva algums em forma de backup, em uma pasta separada especifica, e tambem salva os objts construidos originais. todos objts podem ser importados facilmente.
	Economizar-Memoria: Em Mundos muito grandes P3X ajusta memoria automaticamente, ele remove da memoria objts que estão muito distantes da camera, para aliviar carga de memória, e os importa novamente quando camera esta se aproximando, este efeito pode ser interrompido em configurações para modo Cientifico, no qual física funciona no mundo inteiro sem depender da camera.
	
-----------------------------------IA---------------------------------------------
	hoje não á como mais fugir, ia veio pra ficar, então vamos aproveitar e utiliza-la para ascelerar ainda mais o workflow do usuário, e tambem garantir mais performance e qualidade.
	
	IA-Modificadores:
	otimizar normals das moléculas para decimate mais preciso
	ajustar vibrações para iluminações realistas
	decidir densidade ideal por região da scene
	prever densidade futura
	atuar no renderer
	atuar como “Diretor Técnico Assistido”
	sugerir configs rápidas com base no estilo do usuário
	criar presets automáticos (“cinematico”, “cientifico”, “pcs-fracos”, etc.)
	detectar gargalos e redistribuir orçamento em FraPrite.
	dentre muitos outros.
	upscale-Image/Video.(eleva resolução final do RENDERIZAR).
	

Introdução de IA é um outro departamento, que pode ser instalado a parte, alem desta possibilidade P3X possibilita que usuários posam adicionar modelo próprio de IA.

	EXTAS:
		integração pode utilizar voz, para agilizar processos, e a composição da scene poderemos simplesmente pedir a ia para espalhar objetos pela scene etc... tudo por comando texto ou voz. mesmo que os modelos 3d sejam feitos totalmente por usuário, poderemos pedir a IA para modificar algo no modelo etc.. então o ambiente 3d será fantastico ja que a IA conseguira agilizar muitos passos. e o workflow ficara imprecionante.
		
		APRENDIZADO-MODO:
			 tambem pensei em talvez os IA-UBINs por ex: em uma molecula, se tornarem uma coisa chamada aprendizado. ou seja, se eu quero mover um obj, eu o movo e salvo isto então ele entende que tem que se mover, e posso explicar por voz ou texto que o obj deve se mover a apertar tal tecla, ou ouvir um comando especifico etc... então inicialmente para o baque não ser muito grande eu ainda insiro algumas coisas que encontramos em egines comuns tanto editores de texto de imagem de filmes de games etc.. porem ja tem um caminho traçado para o futuro onde muito do proprio p3x ira mudar para ficar ainda mais intuitivo e facil de usar e manipular objts.

--------------------------------------TECNICAS-FUNCINAMENTOS--------------------------------------------

DEFORMAÇÂO-MALHA:(sistema de elevate/reduce pode ajudar a encontrar a solução).
1-	ocasionalmente em animações e colisões de física, o obj pode se deformar de modo que atomos se distanciam, ocasionando assim uma fisura na malha, o intuito dessa trava é impedir que visualmente o obj se rompa, sendo assim ha uma dinamica que constroi em realtime novos pixels aonde falta, este proscesso acontece antes do renderer.(devo desenvolver melhor esta tecnica, considerar escalonamento de pixels.)
	
2-	em animações pode orcoorer a sobreposição de Atomos para que obj tenha efeito de encolhimento em algumas partes, isto deve ocorrer, no entanto ha coisas a se considerar, como qual pixel terá influencia para renderer. os 2 ou mais atomos no mesmo ponto ainda tem suas propriedades diferentes para que não comprometa física/animações, entretanto a localização original não será modificada, permitindo que obj retorne seu formato original.(estudar como isto será aplicado na pratica)


DEPARTAMENTOS:
	cada departamento é um módo de funcionamento do MOTOR P3X, por ex: o departamento de edição, voce edita o obj 3D. é como uma aba especifica. isso é importante porque os departamentos, vão ser a base, para a distribuição de P3X.
    
MOVIMENTAÇÂO DE OBJTS:
	para mover camera ou qualquer outro obj é simples, como o grid do mundo é fixo e pré determinado ja temos todos os pontos possiveis do mundo carregados em arrays. os objts tambem tem seus átomos posicionados em arrays, bastando assim simplesmente arrastár a referencia do obj para mundo no array.
	

ROTAÇÂO:
	para rotacionar, é um pouco mais complexo porque é nescessário utilizar operações matemáticas e visualmente para mundos de escalas 4,8,16 pixels por pontos, podem criar saltos muito grandes e tambem obrigar que mais de um átomo ocupe o mesmo lugar.
	
	
	
ESCALA:
	Basta referenciar que 1pixel - 1cm, ou 2cm ou 10cm e assim voce ja tem um parametro de tamanho de obj. pode tambem selecionar escala 2pixels,4pixels etc... mantendo a referencia em 1cm por ex. então voce pode ter a combinação que quiser, para alcançar o estilo gráfico desejado e medidas. vale lembrar que como o mundo é discréto, não temos pontos intermediarios flutuantes, então para maior prescisão deve-se criar objetos muito maiores e definir que por ex 1 pixel vale 1mm. assim consegue-se mais presisão, e para tornar mais leve basta utilizar salto maior como por ex 10pixels por ponto.
	
	
ALPHA:
	deveremos pensar em atomos com informação alpha, ou seja que permite a visibilidade de pontos que estão em camadas anteriores a ele na perspectiva da camera. alpha é mensurado de 0.0(totalmente opaco) a 1.0(totalmente transparente), somente objetos que contem mais de 0.0 de alpha são interpretados pelo renderer, para trata-los. se um obj contem todos atomos com 0.0 de alpha ele não passa pelo proscesso de blend.
	
	Alpha-Camera-Renge: na camera ha um ajuste em porcentagem de quanto de profundidade alpha deve ser proscessado, sendo assim podemos selecionar por ex: ate 50% da profundidade haverá alpha, apos isto o restante será desconsiderádo, isto serve para acelerar o renderer, a custo de pouca queda grafica.
	
	Alpha_Check: no renderer ha nescecidade de checar os objts que estão com alpha, a serem contabilizados, no entanto ainda que esta medida seja buscando economizar proscessamento, em casos de scenas lotadas de alpha, o teste irá mais atrapalhar que ajudar, então o usuário pode desabilitar o alpha-check, e o renderer tratará tudo como alpha, tratando cada átomo matematicamente com blend alpha, para atomos 0.0 não fará diferença visual.
	
	Alpha_precisão: naturalmente quanto mais casas decimais tivermos em float 0.00000, mais presisão temos, então aqui esta a configuração de presisao de alpha.
	
	
FAKE-ATOMOS:
	átomos criados provisoriamente para manter continuidade de malha, atua em momentos onde obj se deforma esticando-se, assim nescecitando de novos pixels para impedir "buracos" na malha. pode ser gerado de algumas formas:
		repetir	: repete o pixel proximo com caracteristicas identicas.
		suave	: cria pixel baseado na media dos pixels proximos.
		
INTRA-EXPANDIR:
	é um check-box que se marcado indica ao P3X que o obj se deformará de forma em que ao se expandir, jogará as malhas internas para fora. INTRA-EXPANDIR espera um kit de grupos para informar ordem de retiarda interna para fora do modelo(cria grupo, seleciona moleculas, nomeia o grupo, adiciona no kit, a ordem indica qual malha sai primeiro), caso não especifique o grupo P3X tentará adivinhar, porem pode causar alguns bugs.
	
-------------------------------EXPERIMENTOS PRATICOS--------------------------------------------------------------------

1- Podemos iniciar criando um GRID, representando-o com pixels/Atomos soltos, estes átomos podem ser montados contendo suas propriedades referenciando por ex cores, e então podemos fazer um trasejado X,Y,Z, com este trasejo ainda devemos determinar o tamanho final do mundo, para que a linha não seja ifinita. podemos tambem fazer com que a linha seja dinamica e então ela podera ser ifinita. alem disto podemos testar a camera e o renderer, tudo isto em um único teste, alem de esperimentar rotações e movimentação de camera.

2- Agora podemos experienciar com um cubo basico, totalmente volumetrico, e o mover e rotacionar, dando certo testar com cubo oco, se tudo ocorrer bem iniciar proscesso de maximate/decimate.


-----------------------------------IMAGINE--------------------------------------

1- imagina os vidros, copos recipientes, podemos ate montar um obj dentro de outro no final da scene e ainda adicionar fisica real como por ex um pote de vidro com uma rosquinha dentro, ao mover o pote a rosquinha vai bater no vidro. e o vidro ainda pode ter espessura real pois pode ter varias camadas duplicadas encolhidas para representar volume. o pote tambem pode ter nativamente na egine um mark_phisic, para que o obj interno colida com a camada interna do vidro. este motor p3x não é só um game egine. é muito mais que isso, ele pode ser vfx para os filmes, pode ser filme totalmente 3d. pode ter integração com som 3d. perfeitamente tudo rodando na tela. é um novo blender muito superior, porque é multiuso. pode servir ate para simulações de ia por ex para carros automos ao tirar fotos do asfalto, converte em 3d para ter mais nosção de espacialidade. etc.... temos muita coisa pela frente, porem me parece que eu realmente consegui ajudar o mundo da tecnologia a dar um grande salto.

2-tambem há ideias sobre cabelos, pelos, metais, fios linhas, condutibilidade eletrica, materiais magnéticos, materiais soluveis(sal açucar), evaporação da agua, pressão etc.. e isto tudo seria uma forma da representação realistica. porem devemos lembrar que não é só isso que quero. o p3x deverá permitir coisas que não existem como uma realidade alternativa, ou novos comportamentos de luz, ou simplesmente coisas fantasiosas, estilos low poly (serão ultrapaçados mais pode ser nostaugico) objetos de cores sólidas. etc.. comportamentos FÍSICOS e QUIMICOS devem ser bem elaborados.

3-imagine que ao ligar o computador, ja abre logo um ambiente totalmente diferente. com profundidade. o usuario pode não só como usar o ambiente 3d para se organizar melhor, como tambem uma integração total com IA, torna muita coisa autonoma. o usuario diz por comando de voz e o pc atua dirétamente no p3x. o browser talvez se torne obsoleto, pois a navegação de internet pode ser totalmente diferente. talvez o funcionamento do motor p3x em termos computacionais, supere ate o funcionamento 2d de egines e interfaces graficas. talvez seja o sistema mais simples e completo ao mesmo tempo. mais por hora não vamos tirar os pes do chão kk. 

-------------------------------CONFIGURAÇÔES/PERFORMANCE----------------------------------------------------------------------------------------------

Átomo-float-properts: ajuste de casas decimais de propriedades de átomos, para mais precisão nas cores.

Luz-calcule: r-decimate/rmaximate antes, ou depois.(define se vai calcular luz e efeitos de luz antes do decimate ou depois, isto impacta na performance, e visual não tanto.)

Decimate/Maximate kit: defina qualidade: Game,View,Cinema,Cientifico.(isto define quanto o kit atua e tambe a ordem de atuação, não só como isto mais tambem a forma de atuar no Global, fora da camera.

FraPriTe-FPS: 120, 90, 75, 60, 45, 30, 20.

Física-mundo: voce celeciona formas de calcular: ultra-realistico, realismo-baixo, estilizado, etc... persoalizado.... 
Física-camera: (vale só pra objts que aparecem na camera), desabilitar, realistico, rapido etc...
Física-Mundo-Completo: ativa física independente da camera, isto desabilita Economizar-Memoria. sem-decimate, decimate-leve, decimate-pesado, desabilitar.


------------------------------DISTRIBUIÇÃO-P3X------------------------------------------------

	A ideia é:
		fazer P3X totalmente modular, onde as peças se emcaicham porem não precisa uma das outras, ou seja, teremos um App renderer, teremos um App esculpt etc... então voce quer só visualizar objts 3D.p3x? simples baixe apenas o p3xview+p3xrenderer. então voce instala no pc ou no mobile, qualquer lugar, e voce consegue sómente oque precisa, isto é importante porque p3x não é só um motor para game, ele tambem pode ser utilizado para varias funcionalidades. desde arquitetura, ciencia, medicina etc... e o motivo principal do projeto ser assim é que se quebrarmos alguma parte durante desenvolvimento/otimizações, não quebramos o programa todo, e fica mais facil concertar.
	
	um visualizador de objts p3x. este seria um app que pode rodar em tudo (linux,windows,ios,android,smartv,web) ele lê o obj que pode ser tanto o original, como tambem algum ja comprimido/expandido (ajustado), este app(departamento) poderá visualizar o objt e fazer coisas especificas somente para obj. ex: gerar novo modelo com nova densidade, pintura, animações, normais etc.. cada app utilizara somente 1 arquivo de configurações, que serve para todos apps. então o usuario por ex que só quer usar app de modelos 3d, sem intuito de fazer um game, um filme, contabilizar fisica etc.. usa este app (visualizador/editor de modelos p3x), ele tambem tem por padrão Luzes base (estilo matcaps do blender) para que o usuario possa enchergar o modelo, ja que sem luz não tem como ver nada, e não existe unshaded então existe uma super Luz que simula isto. 
	mais por ex um segundo app que simula fisica. porem todos eles se unem. no caso se eu coloco os 2 apps na mesma pasta ao abrir um ou o outro tanto faz. os 2 apps se fundem na execução, e fica como se fosse 2 abas abertas do mesmo sistema. e não só pra isto mais tambem para todos os outros apps. claro temos limitações, em web por ex não ha pastas então a forma de lidar com isto é: usuario seleciona oque quer abrir, e se quer abrir outra parte do software ele clica e ele sera carregado. então terá abas. isto faz com que o programa seja mais modular e seja encaixavel. inclusive a parte de IA tambem tera o app exclusivo separado. dai usuario abre a aba de ia para editar os modelos desejados, a ia faz oque precisa e o usuario fexa a aba. isso sim é futuro etc..etc.. ja pode imaginar a gama de possibilidades?, empresas poderão fazer seus proprios pedaços e acopla-los em partes especificas de p3x, tornando ainda mais versatil.

-----------------------------------ERROS/FEEDBACK------------------------------------------
	P3X deve conter possibilidade de enviar erros e feedback de usuários para densevolvedores, no qual corrigem e otimizão-o.
	
----------------------------------BDD-----------------------------------------------------

	P3X deve existir um banco de dados, onde usuários podem compartilhar seus modelos/projetos/propriedades/configs etc.. crescendo assim a game de facilidades para todos.
	podemos assim aproveitar partes feitas de vários colaboradores usuários e montar um cenário rapidamente. IA pode auxiliar no proscesso de baixar e montar os objts no MUNDO.

-----------------BENEFICIOS DE P3X-----------------------------


TECNOLOGIAS ULTRAPASSADAS:
	
	
	subsurface				: automático.		(vem de graça, faz malhas internas com vibrações e absorsão diferente, trazendo subsurface gratis)
	culling					: automático.		(vem de graça, pela forma de renderizar do fundo para frente)
	sincronização vertical	: Não existe.		(FraPriTe resolve isto)
	z-index,z-buffer		: Não existe.		(renderer joga no buffer os átomos do fundo para frente, utilizando o contato real como parametro)
	Vertices,Arestas,Faces	: Não existe. 		(apenas atomos/pixels para representar tudo)
	UV						: Não existe. 		(sem retopologia haha)
	textures				: Não existe. 		(informação de cor ja existe no atomo/luz)
	Normal					: Não existe. 		(todos pixels apontão para tela)
	RGB colors				: Reinterpretado.	(vibração 0.0 a 1.0)
	Luz,sombra				: Reinterpretado.	(definido pelo obj real volumétrico luz de contato, gera sombra naturalmente de graça)
	alpha:	  				: Reinterpretado.	(tratado como alpha 2D, tratado por camadas de pixels acumulados no buffer)
	Renderer   				: Reinterpretado.	(reformulado, otimizado, super rápido e otimizado/organizado, alem de configuravel)
	colisão					: Reinterpretado.	(por contato real entre moléculas)
	
CONSEQUENCIAS:
	
	game-egine		: uma nova forma de se desenvolver games muito facil e mais realistico, estilizados tambem tem seu lugar
	filmes			: muito mais densos, detalhados, facil renderização, IA ajuda muito a preparar objetos e ações.
	Mobile			: fótos po de-maximate,dem ser totalmente 3D com IA, filmes interagidos, UIs para celular, Som interagido 3D etc...
	Formatos		: novos formatos de video e som surgirão, formatos de dados tambem podem ser mais otimizados, filmes podem ser interativos internamente.
	
	
	
	Alem das consequencias que serão de impacto imediato, tambem virá a consequencia de forma indiréta, muitas marcas vão poder utilizar de P3X para desenvolver coisas novas inimaginaveis.
	Como P3X é uma quebra de paradigmas, visto que sua implementação é simples e atinge um resultado imprecionante, muitos se inspirarão e logo será desenvolvido outras coisas que nada tem aver com 3D ou mesmo computação, porem com esta nova perspectia que P3X traz.
	Web pode ficar ultrapassado. então ou P3X terá uma web interna como um app web que substitui os webs antigos, ou P3X roda dentro de web comun, para publicos especificos que precisam de projetos rapidos etc..
	
	
	P3X não tem limites.
		
-----------------------------------------------FIM---------------------------------------------------------


	Para tornar P3X realidade, desenvolvi um outro projeto chamado UBIN, ele é uma linguagem de programação(tambem uma quebra de paradigmas), Ubin trabalha no baixonivel e autonivel ao mesmo tempo, para atingirmos o maximo de performance no software, e ser facil construi-lo. Quando fui iniciar o proscesso de descisão de qual linguagem usaria para tornar P3X realidade, percebi que estamos limitados a c, c++ assembly. e ainda temos problemas com apis Vulkan ou Webgl, devido a falta de controlhe absoluto na maquina e despadronização de hardwares, então precisei desenvolver este método para construir softwares.
	Para mais informações visitem o projeto UBIN.
	
	











