---
title: 'Access (Web 应用的 Year 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a70751eb-bfde-4f7d-ad90-a1e4cca25dbc
description: 返回一个数值，表示公历中指定日期的年份。
ms.openlocfilehash: 1400c352bcc070035d15b46f8e547e4637364299
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433120"
---
# <a name="year-function-access-custom-web-app"></a>Access (Web 应用的 Year 函数) 

返回一个数值，表示公历中指定日期的年份。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Year** (*Date*)  
  
Year 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Date*  <br/> |可以解析为"日期/时间"值的表达式。 *Date* 参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
   
## <a name="remarks"></a>备注

Year、Month和 **Day** 函数返回的值将为公历值，而不考虑提供的日期值的显示格式。 例如，如果提供的日期的显示格式使用回历，则 **Year、Month** 和 **Day** 函数的返回值将是与等效公历日期相关联的值。 
  

