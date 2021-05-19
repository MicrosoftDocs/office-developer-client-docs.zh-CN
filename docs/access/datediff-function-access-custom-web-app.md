---
title: 'Access 自定义 Web (应用程序的 DateDiff) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1c58ee87-0f57-4643-be4d-62da815df705
description: 返回指定的开始日期和结束日期之间跨越的指定日期部分边界的计数。
ms.openlocfilehash: 1cce8a501c5a57384372e681f903baa4f4c20bef
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415612"
---
# <a name="datediff-function-access-custom-web-app"></a>Access 自定义 Web (应用程序的 DateDiff) 

返回指定的开始日期和结束日期之间跨越的指定日期部分边界的计数。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateDiff** (DatePart、StartDate、EndDate)    
  
**DateDiff** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |是  *StartDate 和*  *EndDate*  的一部分，用于指定跨边界的类型。 有关有效设置的列表，请参阅"备注"部分。  <br/> |
| *StartDate*  <br/> |可以解析为"日期/时间"值的表达式。 *Date* 参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
| *EndDate*  <br/> |可以解析为"日期/时间"值的表达式。 *Date* 参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
   
## <a name="remarks"></a>备注

下表列出了所有有效的  *DatePart*  参数。 
  
|***DatePart***|
|:-----|
|**year** <br/> |
|**quarter** <br/> |
|**month** <br/> |
|**dayofyear** <br/> |
|**day** <br/> |
|**week** <br/> |
|**hour** <br/> |
|**minute** <br/> |
|**second** <br/> |
|**毫秒** <br/> |
   

