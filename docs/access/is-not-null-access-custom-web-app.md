---
title: '[不] 是 NULL （访问自定义 web 应用程序）'
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b941a0c7-9753-4920-bb6d-cbba94ba9422
description: 确定指定的表达式是否为 NULL。
ms.openlocfilehash: fcbceb1e8edac65fe232ba9c2b12195b99db9545
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773452"
---
# <a name="is-not-null-access-custom-web-app"></a>[不] 是 NULL （访问自定义 web 应用程序）

确定指定的表达式是否为 NULL。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *表达式***IS**[ ** ]**NULL**
  
**IS [NOT] NULL**谓词包含下列参数。 
  
|||
|:-----|:-----|
| *expression*  <br/> |任何有效的表达式。  <br/> |
| *NOT*  <br/> |指定布尔值的结果取反。 谓词取消其返回值，如果的值不是 NULL 值和 FALSE 如果值为 NULL，则返回 TRUE。  <br/> |
   
## <a name="remarks"></a>说明

如果*表达式*的值为 NULL，则为 NULL，则返回 TRUE;否则，将返回 FALSE。 
  
如果表达式的值为 NULL，则不是 NULL 返回 FALSE;否则，将返回 TRUE。
  

