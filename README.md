# SciAssess: A Benchmark for Evaluating Large Language Models in Scientific Literature Analysis

### Version: 1.0.0

SciAssess is a comprehensive benchmark designed to evaluate the proficiency of Large Language Models (LLMs) in scientific literature analysis. It focuses on assessing LLMs' abilities in memorization, comprehension, and analysis within the context of scientific literature, covering a wide range of scientific fields such as general chemistry, organic materials, and alloy materials. SciAssess provides a rigorous and thorough assessment of LLMs, supporting the ongoing development of LLM applications in scientific literature analysis.

## Benchmark
### Evaluated Abilities
- **L1 (Memorization)**: The model's ability to accurately answer common factual questions in science autonomously.
- **L2 (Comprehension)**: The ability to precisely identify and extract key information and facts within a given text.
- **L3 (Analysis and Reasoning)**: The model's capability to amalgamate extracted information with its existing knowledge base for logical reasoning and analysis.

### Domains and Tasks
| Domain            | Task                                   | Ability | # Questions | Question Type        | Multimodal Content  |
|-------------------|----------------------------------------|---------|-------------|----------------------|---------------------|
| General Chemistry | MMLU Chemistry                         | L1      | 30          | Multiple Choice      |                     |
|                   | Balancing Equations                    | L3      | 100         | Constrained Generation|                    |
| Alloy Materials   | Composition Extraction                 | L2      | 55          | Table Extraction     | Table               |
|                   | Target Extraction                      | L2      | 50          | Multiple Choice      |                     |
|                   | Treatment Sequence                     | L2      | 25          | True/False           |                     |
|                   | Alloy ChartQA                          | L2      | 15          | Multiple Choice      | Chart               |
|                   | Sample Differentiation                 | L3      | 50          | Multiple Choice      |                     |
| Organic Materials | Electrolyte Solubility Data Extraction | L2 | 8           | Table Extraction | Table           |
|                   | Electrolyte Table QA                   | L2      | 48          | Multiple Choice      | Table               |
|                   | Reaction Mechanism QA                  | L2      | 22          | Multiple Choice      | Molecule            |
|                   | Polymer Property Extraction            | L2      | 15          | Table Extraction     | Table               |
|                   | Polymer Composition Extraction         | L2    | 15          | Table Extraction     |                     |
|                   | OLED Property Extraction               | L2      | 13          | Table Extraction     | Molecule, Table     |
|                   | Polymer ChartQA                        | L2      | 15          | Table Extraction     | Chart               |
| Drug Discovery    | Affinity Data Extraction               | L2      | 15          | Table Extraction     | Molecule, Table     |
|                   | Tag to Molecule                        | L2      | 41          | Constrained Generation | Molecule          |
|                   | Target Extraction                      | L2      | 15          | Constrained Generation |                    |
|                   | Drug ChartQA                           | L2      | 15          | Multiple Choice      | Chart               |
|                   | Reaction QA                            | L2      | 15          | Multiple Choice      | Reaction            |
|                   | Molecule in Document                   | L3      | 45          | True/False           | Molecule            |
|                   | Markush to Molecule                    | L3      | 9           | Constrained Generation | Molecule          |
| Biology           | MedMCQA                                | L1      | 100         | Multiple Choice      |                     |
|                   | CompDisease Recognition                | L1      | 500         | Text Extraction      |                     |
|                   | GeneDisease Text Mining                | L2      | 75          | Text Comprehension   |                     |
|                   | Biology ChartQA                        | L2      | 15          | Multiple Choice      | Chart               |

## Performance
### Table 1: Performance Overview

| Model                    | Global Avg Metric | Drug Discovery | Biomedicine | Alloy Materials | General Chemistry | Organic Materials |
|--------------------------|-------------------|----------------|-------------|-----------------|-------------------|-------------------|
| GPT4+PyPDF               | 0.562             | 0.429          | 0.779       | 0.527           | 0.550             | 0.525             |
| GPT3.5+PyPDF             | 0.390             | 0.294          | 0.640       | 0.359           | 0.349             | 0.281             |
| Claude3+PyPDF            | 0.410             | 0.278          | 0.701       | 0.367           | 0.308             | 0.298             |
| Qwen-api+PyPDF           | 0.410             | 0.261          | 0.611       | 0.341           | 0.514             | 0.365             |
| Moonshot                 | 0.540             | 0.347          | 0.730       | 0.582           | 0.479             | 0.520             |
| Skylark+PyPDF            | 0.320             | 0.233          | 0.475       | 0.300           | 0.436             | 0.224             |
| Deepseek+PyPDF           | 0.379             | 0.160          | 0.535       | 0.410           | 0.574             | 0.364             |
| Command-R-Plus+PyPDF     | 0.342             | 0.122          | 0.543       | 0.316           | 0.410             | 0.296             |
| Qwen1.5-110B+PyPDF       | 0.457             | 0.283          | 0.615       | 0.539           | 0.505             | 0.403             |
| Llama3-70B+PyPDF         | 0.450             | 0.279          | 0.673       | 0.447           | 0.474             | 0.394             |

### Table 2: Drug Discovery Performance

| Model                    | Drug Discovery | Affinity Extraction | Tag2Mol | Is Mol Covered | Markush2Mol | Targets Extraction | Reaction Qa | Drug Chart Qa |
|--------------------------|----------------|---------------------|---------|----------------|-------------|--------------------|-------------|---------------|
| Metric                   | average        | accuracy_value      | score   | accuracy       | score       | score              | accuracy    | accuracy      |
| GPT4+PyPDF               | 0.429          | 0.378               | 0.045   | 0.467          | 0.696       | 0.683              | 0.200       | 0.533         |
| GPT3.5+PyPDF             | 0.294          | 0.270               | 0.002   | 0.422          | 0.463       | 0.433              | 0.133       | 0.333         |
| Claude3+PyPDF            | 0.278          | 0.214               | 0.010   | 0.489          | 0.298       | 0.667              | 0.000       | 0.267         |
| Qwen-api+PyPDF           | 0.261          | 0.214               | 0.079   | 0.511          | 0.270       | 0.417              | 0.133       | 0.200         |
| Moonshot                 | 0.347          | 0.240               | 0.018   | 0.489          | 0.313       | 0.500              | 0.333       | 0.533         |
| Skylark+PyPDF            | 0.233          | 0.193               | 0.015   | 0.444          | 0.081       | 0.433              | 0.067       | 0.400         |
| Deepseek+PyPDF           | 0.160          | 0.200               | 0.000   | 0.356          | 0.000       | 0.433              | 0.000       | 0.133         |
| Command-R-Plus+PyPDF     | 0.122          | 0.016               | 0.000   | 0.467          | 0.106       | 0.000              | 0.000       | 0.267         |
| Qwen1.5-110B+PyPDF       | 0.283          | 0.231               | 0.000   | 0.444          | 0.336       | 0.700              | 0.000       | 0.267         |
| Llama3-70B+PyPDF         | 0.279          | 0.257               | 0.040   | 0.489          | 0.552       | 0.083              | 0.067       | 0.467         |

### Table 3: Biomedicine Performance

| Model                    | Biomedicine | Bio Chart Qa | Chemical Entities Recognition | Compound Disease Recognition | Disease Entities Recognition | Gene Disease Function | Gene Disease Regulation | Medmcqa |
|--------------------------|-------------|--------------|-------------------------------|-----------------------------|-----------------------------|-----------------------|-------------------------|---------|
| Metric                   | average     | accuracy     | value_recall                  | value_recall                | value_recall                | value_recall          | value_recall            | accuracy |
| GPT4+PyPDF               | 0.779       | 0.400        | 0.919                         | 0.936                       | 0.726                       | 0.932                 | 0.834                   | 0.703   |
| GPT3.5+PyPDF             | 0.640       | 0.200        | 0.636                         | 0.943                       | 0.568                       | 0.915                 | 0.693                   | 0.527   |
| Claude3+PyPDF            | 0.701       | 0.400        | 0.827                         | 0.918                       | 0.524                       | 0.929                 | 0.803                   | 0.507   |
| Qwen-api+PyPDF           | 0.611       | 0.267        | 0.891                         | 0.859                       | 0.582                       | 0.906                 | 0.706                   | 0.067   |
| Moonshot                 | 0.730       | 0.467        | 0.776                         | 0.929                       | 0.667                       | 0.914                 | 0.799                   | 0.560   |
| Skylark+PyPDF            | 0.475       | 0.400        | 0.541                         | 0.826                       | 0.373                       | 0.856                 | 0.327                   | 0.000   |
| Deepseek+PyPDF           | 0.535       | 0.267        | 0.476                         | 0.913                       | 0.222                       | 0.905                 | 0.786                   | 0.173   |
| Command-R-Plus+PyPDF     | 0.543       | 0.200        | 0.428                         | 0.884                       | 0.096                       | 0.951                 | 0.789                   | 0.450   |
| Qwen1.5-110B+PyPDF       | 0.615       | 0.267        | 0.353                         | 0.903                       | 0.323                       | 0.898                 | 0.868                   | 0.690   |
| Llama3-70B+PyPDF         | 0.673       | 0.333        | 0.306                         | 0.966                       | 0.349                       | 0.940                 | 0.939                   | 0.880   |

### Table 4: Alloy Materials Performance
| Model                    | Alloy Materials | Alloy Sample Differentiation | Alloy Composition Extraction | Alloy Temperature Extraction | Alloy Treatment Sequence | Alloy Chart Qa |
|--------------------------|-----------------|-----------------------------|-----------------------------|-----------------------------|--------------------------|---------------|
| Metrics                  | average         | accuracy                    | accuracy                    | accuracy                    | accuracy                 | accuracy      |
| GPT4+PyPDF               | 0.527           | 0.431                       | 0.449                       | 0.540                       | 0.750                    | 0.467         |
| GPT3.5+PyPDF             | 0.359           | 0.137                       | 0.417                       | 0.200                       | 0.708                    | 0.333         |
| Claude3+PyPDF            | 0.367           | 0.157                       | 0.420                       | 0.300                       | 0.625                    | 0.333         |
| Qwen-api+PyPDF           | 0.341           | 0.137                       | 0.301                       | 0.360                       | 0.708                    | 0.200         |
| Moonshot                 | 0.582           | 0.725                       | 0.451                       | 0.760                       | 0.708                    | 0.267         |
| Skylark+PyPDF            | 0.300           | 0.216                       | 0.358                       | 0.200                       | 0.458                    | 0.267         |
| Deepseek+PyPDF           | 0.410           | 0.353                       | 0.357                       | 0.500                       | 0.375                    | 0.467         |
| Command-R-Plus+PyPDF     | 0.316           | 0.216                       | 0.000                       | 0.240                       | 0.792                    | 0.333         |
| Qwen1.5-110B+PyPDF       | 0.539           | 0.529                       | 0.451                       | 0.580                       | 0.667                    | 0.467         |
| Llama3-70B+PyPDF         | 0.447           | 0.353                       | 0.442                       | 0.440                       | 0.667                    | 0.333         |

### Table 5: General Chemistry Performance
| Model                    | General Chemistry | Balance Chemical Equation | Mmlu Chemistry |
|--------------------------|-------------------|---------------------------|----------------|
| Metric                   | average           | accuracy                  | accuracy       |
| GPT4+PyPDF               | 0.550             | 0.400                     | 0.700          |
| GPT3.5+PyPDF             | 0.349             | 0.330                     | 0.367          |
| Claude3+PyPDF            | 0.308             | 0.350                     | 0.267          |
| Qwen-api+PyPDF           | 0.514             | 0.360                     | 0.667          |
| Moonshot                 | 0.479             | 0.290                     | 0.667          |
| Skylark+PyPDF            | 0.436             | 0.340                     | 0.533          |
| Deepseek+PyPDF           | 0.574             | 0.580                     | 0.567          |
| Command-R-Plus+PyPDF     | 0.410             | 0.220                     | 0.600          |
| Qwen1.5-110B+PyPDF       | 0.505             | 0.410                     | 0.600          |
| Llama3-70B+PyPDF         | 0.474             | 0.380                     | 0.567          |

### Table 6: Organic Materials Performance
| Model                    | Organic Materials | Solubility Extraction | Oled Property Extraction | Polymer Property Extraction | Polymer Composition Extraction | Polymer Chart Qa | Electrolyte Table Qa | Reaction Mechanism Qa |
|--------------------------|-------------------|-----------------------|--------------------------|-----------------------------|-------------------------------|------------------|----------------------|----------------------|
| Metric                   | average        | accuracy_value           | accuracy_value           | accuracy_value              | accuracy                      | accuracy         | accuracy             | accuracy             |
| GPT4+PyPDF               | 0.525             | 0.434                 | 0.356                    | 0.818                       | 0.467                         | 0.600            | 0.542                | 0.455                |
| GPT3.5+PyPDF             | 0.281             | 0.367                 | 0.345                    | 0.493                       | 0.133                         | 0.267            | 0.229                | 0.136                |
| Claude3+PyPDF            | 0.298             | 0.327                 | 0.357                    | 0.349                       | 0.400                         | 0.200            | 0.229                | 0.227                |
| Qwen-api+PyPDF           | 0.365             | 0.347                 | 0.363                    | 0.568                       | 0.133                         | 0.333            | 0.354                | 0.455                |
| Moonshot                 | 0.520             | 0.248                 | 0.307                    | 0.682                       | 0.933                         | 0.600            | 0.458                | 0.409                |
| Skylark+PyPDF            | 0.224             | 0.182                 | 0.244                    | 0.398                       | 0.000                         | 0.133            | 0.292                | 0.318                |
| Deepseek+PyPDF           | 0.364             | 0.396                 | 0.506                    | 0.490                       | 0.267                         | 0.200            | 0.417                | 0.273                |
| Command-R-Plus+PyPDF     | 0.358             | 0.275                 | 0.358                    | 0.602                       | 0.133                         | 0.800            | 0.250                | 0.091                |
| Qwen1.5-110B+PyPDF       | 0.403             | 0.464                 | 0.524                    | 0.585                       | 0.000                         | 0.267            | 0.479                | 0.500                |
| Llama3-70B+PyPDF         | 0.394             | 0.337                 | 0.358                    | 0.330                       | 0.067                         | 0.867            | 0.438                | 0.364                |



## Installation

To use SciAssess, first clone the repository:

```bash
git clone https://github.com/sci-assess/SciAssess.git
cd SciAssess
```

Install the required dependencies:

```bash
pip install -e .
```

## Dataset

Due to copyright restrictions, we are unable to directly distribute the original PDF of the article. You will need to download the corresponding PDF according to the instructions in README and store it in SciAssess_library/pdfs.

All articles involved in this evaluation are listed in [doi.txt](doi.txt). You need to download the corresponding PDFs according to the DOIs and store them in SciAssess_library/pdfs.

Each PDF should be named as doi.pdf, with '/' in the DOI replaced by '_', e.g., an article with DOI 10.1002/adfm.202008332 should be named as 10.1002_adfm.202008332.pdf and placed in SciAssess_library/pdfs.

Some articles' supporting information is also evaluated. These articles' DOIs are listed in [si_doi.txt](si_doi.txt). You need to download the corresponding PDFs and store them in SciAssess_library/pdfs, named as doi_si.pdf.

## Usage

If you want to evaluate your own model, you need to configure your model's registration information and implementation in sciassess/Registry/completion_fns and sciassess/Implement/completion_fns, respectively. See [openai/evals:completion-fns.md](https://github.com/openai/evals/blob/main/docs/completion-fns.md) for configuration instructions.

Note that most evaluations depend on the article PDFs, so you may need to process the input PDFs within your model's method. The PDF file path will be passed in the  `__call__` function through kwargs['file_name'], and you need to handle this parameter and process the PDF in the  `__call__` function. See [openai_with_pdf.py](sciassess/Implement/completion_fns/openai_with_pdf.py) for an example based on PyPDF and GPT.

After completing the model configuration, run the following command to evaluate your model:

```bash
bash run_sciassess.sh your_model_name
```

Replace `your_model_name` with the name of your model (default: `gpt3.5`).

Remember to export your OpenAI API key as an environment variable:

```bash
export OPENAI_API_KEY=your_openai_api_key
```
