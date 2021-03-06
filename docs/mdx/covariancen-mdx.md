---
title: CovarianceN (многомерные выражения) | Документация Майкрософт
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 796dc37127eba984477aef628e4ae9161db4637e
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "68047182"
---
# <a name="covariancen-mdx"></a>CovarianceN (многомерные выражения)


  Возвращает образец ковариации вычисленных над набором пар значений x-y с помощью формулы несмещенной совокупности (разделяя по количеству пар x-y).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
CovarianceN(Set_Expression, Numeric_Expression_y [ ,Numeric_Expression_x ] )  
```  
  
## <a name="arguments"></a>Аргументы  
 *Set_Expression*  
 Допустимое многомерное выражение, возвращающее набор.  
  
 *Numeric_Expression_y*  
 Допустимое числовое выражение (обычно многомерное выражение координат ячейки), возвращающее число, которое представляет значения по оси Y.  
  
 *Numeric_Expression_x*  
 Допустимое числовое выражение (обычно многомерное выражение координат ячейки), возвращающее число, которое представляет значения по оси X.  
  
## <a name="remarks"></a>Remarks  
 Функция **CovarianceN** вычисляет указанный набор для первого числового выражения, чтобы получить значения для оси y. Затем функция вычисляет указанный набор со вторым числовым выражением (если оно указано), чтобы получить значения для оси X. Если второе числовое выражение не указано, функция использует текущий контекст ячеек в указанном наборе в качестве значений для оси X.  
  
 Функция **CovarianceN** использует формулу несмещенной совокупности. Это отличается от функции [ковариации](../mdx/covariance-mdx.md) , которая использует формулу смещенной совокупности (деление на число пар x-y).  
  
> [!NOTE]  
>  Функция **CovarianceN** игнорирует пустые ячейки или ячейки, содержащие текстовые или логические значения. Однако функция обрабатывает ячейки с нулевыми значениями.  
  
## <a name="see-also"></a>См. также:  
 [Справочник по функциям многомерных выражений (многомерные выражения)](../mdx/mdx-function-reference-mdx.md)  
  
  
