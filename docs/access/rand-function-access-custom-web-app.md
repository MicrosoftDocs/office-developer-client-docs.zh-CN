---
title: 'Rand 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6390b325-025e-4546-bb19-1cd1c45ceb5a
description: 返回一个介于 0 和 1 之间的伪随机数。
ms.openlocfilehash: 02d914de9d74083a6ebf76f6d0e556fe51954a24
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416606"
---
# <a name="rand-function-access-custom-web-app"></a>Rand 函数 (Access 自定义 Web 应用) 

返回一个介于 0 和 1 之间的伪随机数。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Rand** ( [  *Seed*  ])  
  
**Rand** 函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Seed*  <br/> |提供种子值的整数表达式。 如果  *未指定 Seed，*  则随机分配一个种子值。  <br/> |
   
## <a name="remarks"></a>备注

使用相同的种子重复调用 **Rand** 函数将返回相同的结果。 
  

