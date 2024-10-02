# Portifolio
Um projeto iniciante, recriando o jogo Pac-Man.



A finalidade desse projeto é demonstrar um pouco do meu conhecimento através de um jogo funcional, conhecido por muitas pessoas, e de certa forma considerado simples.
Usei o template de ThirdPerson Game para aproveitar a lógica de movimentação e câmera da personagem, já escrita na Unreal Engine.
Criei um material com um único valor de parâmetro (BaseColor) e uma instância desse material para que ele pudesse ser editado individualmente nas Blueprints a seguir.
Criei um ator "BP_masterActor" contendo uma StaticMesh e, no script de construção, defini a variável para o "MI_material" (a instância do material) para que o valor do parâmetro "BaseColor" pudesse ser dinamicamente atualizado.
A partir desse ator pai, criei as blueprints filhas para definir a geometria do level e os pick-ups do jogo.
Para a "BP_masterActorBaseGeometry", eu criei um Enumerator para o tipo de geometria (chão ou parede) e usei para definir o tipo de StaticMesh e a cor para cada um.
Para a "BP_masterActorPickUp", também criei um Enumerator definindo o tipo de PickUp e adicionei uma esfera de colisão para os efeitos de somar a pontuação e chamar a habilidade da personagem de poder causar dano aos inimigos.
Dentro da "BP_ThirdPersonCharacter", já definida pelo template escolhido, defini a variável da instância do mesmo material, para dar cor aos personagens. No gráfico de eventos, criei os eventos "ChangeColors" e "CharacterDeath".
Criei uma "BP_ThirdPersonCharacter_Player". Primeiramente, defini os atores das classes "BP_masterActorPickUp" e "BP_ThirdPersonCharacter_Enemy" que estão presentes no level. Criei também os widgets e defini a HUD.
Criei funções para somar a contagem dos pontos e conferir se todos os PickUps se igualam à quantidade somada dos mesmos no level.
Também criei eventos para o fim do jogo com ramificações para cada ocasião, e o evento "CollectedPowerPickUp", que muda o comportamento e as cores das "BP_ThirdPersonCharacter_Enemy" presentes no level.
Já na "BP_ThirdPersonCharacter_Enemy", também criei uma lógica para o evento "EventCharacterDeath", o comportamento inicial de perseguir a personagem (BP_ThirdPersonCharacter_Player), uma cápsula de colisão para chamar os eventos de "CharacterDeath" corretamente, e a implementação de uma movimentação da inteligência artificial, usando uma "NavMesh" no level, além das mudanças de cores.
