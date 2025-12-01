# Consumo de Água Residencial na Austrália (2014-2022)  
**Análise de Séries Temporais + Estruturas Probabilísticas com Redis**

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Redis](https://img.shields.io/badge/redis-%23DC382D.svg?style=flat&logo=redis&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white)

## Descrição do Projeto
Análise completa de série temporal anual do consumo de água distribuída para residências na Austrália, utilizando dados oficiais do **Australian Bureau of Statistics (ABS)** – Water Account, Australia 2021-22.

**Técnicas aplicadas:**
- Análise exploratória (tendências, médias móveis)
- Autocorrelação (ACF/PACF)
- Modelagem preditiva com **ARIMA(1,1,1)**
- Estruturas probabilísticas em **Redis Cloud**:
  - **HyperLogLog** → cardinalidade de faixas de consumo
  - **Count-Min Sketch** → frequência aproximada de anos com alto consumo

## Dataset
- **Fonte oficial**: Australian Bureau of Statistics (ABS)  
  Link: https://www.abs.gov.au/statistics/environment/environmental-accounts/water-account-australia/latest-release
- **Coleta**: Hidrômetros + relatórios de concessionárias estaduais
- **Período**: 2014-15 a 2021-22 (8 observações anuais)
- **Variável**: Consumo residencial distribuído (Gigalitros – GL)
- **Download automático** no notebook (Célula 2)

## Como Executar
1. Clone o repositório
   ```bash
   git clone https://github.com/SEU_USUARIO/agua-australia-senac.git
   cd agua-australia-senac

2. Crie ambiente (opcional)
```bash
pip install -r requirements.txt
```
3. Abra no Colab ou Jupyter:
→ notebooks/analise_consumo_agua_australia.ipynb

4. Redis Cloud (gratuito):
Crie conta em https://redis.com/labs
Ative o módulo RedisBloom
Cole a URL completa na Célula 7 (já tem exemplo)

Obs: O dataset .xlsx é baixado automaticamente. Não precisa fazer upload.
Resultados Principais

Tendência de queda de ~5% no consumo pós-2019 (políticas de eficiência hídrica)
Previsão ARIMA(1,1,1): ~1.755 GL em 2024-25
Redis:
Apenas 3 faixas de consumo em 8 anos (baixa diversidade)
4 anos com consumo alto (detectados com Count-Min Sketch)
Uso de memória: ~400 bytes vs ~8 KB em pandas

Estrutura do Repositório
```text
├── notebooks/          → Notebook principal
├── sample_data/        → Dataset baixado automaticamente
├── README.md           → Este arquivo
├── enunciado-tema.md   → Enunciado original
```
   
