# eolicEnergy2024.3
Projeto OpenFOAM - README.txt
==============================

Este repositório contém um projeto OpenFOAM com scripts que auxiliam na configuração, execução e limpeza de simulações. Siga as instruções abaixo para configurar o ambiente e rodar os scripts do projeto.

-------------------------------------
Pré-Requisitos
-------------------------------------

1. OpenFOAM 2406  
   O projeto foi desenvolvido e testado com a versão 2406 do OpenFOAM.  
   Download e instruções de instalação: https://openfoam.org/download/

2. ParaView  
   Ferramenta de visualização dos resultados das simulações.  
   Download e instruções de instalação: https://www.paraview.org/download/

-------------------------------------
Instalação
-------------------------------------

1. **Instalando o OpenFOAM 2406:**
   - Acesse a página oficial do OpenFOAM: https://openfoam.org/download/
   - Selecione a versão **2406** e siga as instruções específicas para o seu sistema operacional (Linux, Windows ou macOS).

2. **Instalando o ParaView:**
   - Acesse a página oficial do ParaView: https://www.paraview.org/download/
   - Baixe a versão compatível com o seu sistema operacional e siga as instruções de instalação.

-------------------------------------
Execução dos Scripts do Projeto
-------------------------------------

No diretório deste repositório, você encontrará três scripts principais:

1. **Allrun**
------------------
  **Propósito:**  
   -Automatiza o processo completo do caso de simulação, incluindo a preparação do ambiente, decomposição do domínio para processamento paralelo, execução do solver e reconstrução dos resultados.

   **Como usar:**  
   -Abra um terminal no diretório do projeto e execute:
   
   chmod +x Allrun

   
   ./Allrun

2. **Allmesh**
------------------
  **Propósito:**  
  -Responsável pela geração e configuração da malha do caso de simulação, utilizando ferramentas como `blockMesh` e outras que preparam a geometria.
  
  **Como usar:**  
  -No terminal, execute:
  
  chmod +x Allmesh

  
  ./Allmesh

3. **Allclean**
------------------
**Propósito:**  
-Realiza a limpeza dos arquivos gerados durante as etapas de malha e simulação, permitindo que o projeto seja reiniciado sem resíduos de execuções anteriores.

**Como usar:**  
-No terminal, execute:

  chmod +x Allclean

  
  ./Allclean

-------------------------------------
Configuração do decomposePar
-------------------------------------

O comando `decomposePar` é utilizado para dividir o domínio da simulação em subdomínios, permitindo a execução paralela e a melhor utilização dos recursos computacionais.

**Atenção:**  
Edite o arquivo `decomposeParDict` (geralmente localizado na pasta `system`) e ajuste o parâmetro `numberOfSubdomains` para refletir o número de núcleos disponíveis em seu computador.  
Por exemplo, se seu sistema possui 4 núcleos, configure:

-numberOfSubdomains 4;

Substitua o número “4” pelo total de núcleos do seu computador para otimizar o desempenho da simulação.

-------------------------------------
Considerações Finais
-------------------------------------

- Certifique-se de que todas as dependências (OpenFOAM e ParaView) estejam corretamente instaladas antes de executar os scripts.
- Consulte a documentação oficial do OpenFOAM (https://openfoam.org/documentation/) e do ParaView (https://www.paraview.org/documentation/) para mais detalhes e resolução de dúvidas.
- Mantenha seu sistema atualizado para evitar problemas de compatibilidade.

-------------------------------------
Boa simulação!
