---
title: Determinar a importância de recursos de modelos com a Importância de recursos de permutação no ML.NET
description: Entender a importância de recursos de modelos com a Importância de recursos de permutação no ML.NET
ms.date: 02/01/2019
ms.custom: mvc,how-to
ms.openlocfilehash: a61e5dbbd544aa7df56291db9207343cb6f03e6e
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738806"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Determinar a importância de recursos de modelos com a Importância de recursos de permutação no ML.NET

Ao criar modelos de aprendizado de máquina, muitas vezes não é suficiente simplesmente fazer previsões. Frequentemente, os desenvolvedores de aprendizado de máquina, os tomadores de decisão e aqueles que são afetados pelos modelos precisam entender como os modelos de aprendizado de máquina tomam decisões e quais recursos contribuem para seu desempenho. A `Permutation Feature Importance` (PFI) é uma ferramenta de explicação do modelo que é usada internamente na Microsoft para ajudar os desenvolvedores de aprendizado de máquina a compreender melhor a importância do recurso de modelos.

A PFI é uma técnica para determinar a **importância global do recurso** em um modelo de aprendizado de máquina treinado, motivada por Breiman no [artigo “Random Forests”, seção 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf). A PFI mede a importância do recurso fazendo a pergunta: “Qual seria o efeito no modelo se os valores de um recurso fossem definidos como um aleatórios*?”. A vantagem do método PFI é que ele é independente do modelo (isto é, funciona com qualquer modelo que possa ser avaliado) e pode usar qualquer conjunto de dados, não apenas o conjunto de treinamento, para calcular a importância do recurso. Você pode usar a PFI dessa forma para produzir importâncias de recurso, como este gráfico:

![Gráfico de importância do recurso de permutação](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

Para obter um exemplo de como usar a PFI para analisar a importância do recurso de um modelo, consulte o [repositório do GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).

/* Bem, não é exatamente aleatório, mas permutado no conjunto de exemplos.
