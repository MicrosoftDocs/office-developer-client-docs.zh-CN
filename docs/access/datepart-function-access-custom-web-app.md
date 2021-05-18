---
title: 'Access 自定义 (应用的 DatePart 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8936f0b6-f9b2-44ef-bf90-e482b64611cd
description: 返回一个数值，表示指定日期的指定日期部分。
ms.openlocfilehash: 31ac6423614afd61ed943bb7ba375f14696df1ea
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411433"
---
# <a name="datepart-function-access-custom-web-app"></a>Access 自定义 (应用的 DatePart 函数) 

返回一个数值，表示指定日期的指定日期部分。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DatePart** (*DatePart* *、Date*)  
  
**DatePart** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |Date  *部分 (*  一个日期或时间) 将返回一个整数。 有关有效缩写的列表，请参阅"备注"部分。  <br/> |
| *Date*  <br/> |可以解析为"日期/时间"值的表达式。 *Date* 参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
   
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
|**weekday** <br/> |
|**hour** <br/> |
|**minute** <br/> |
|**second** <br/> |
|**毫秒** <br/> |
   

