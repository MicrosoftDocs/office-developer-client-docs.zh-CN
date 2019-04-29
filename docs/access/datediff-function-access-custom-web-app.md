---
title: DateDiff 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1c58ee87-0f57-4643-be4d-62da815df705
description: 返回在指定的开始日期和结束日期之间交叉的指定日期部分边界的计数。
ms.openlocfilehash: 1cce8a501c5a57384372e681f903baa4f4c20bef
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415612"
---
# <a name="datediff-function-access-custom-web-app"></a>DateDiff 函数 (Access 自定义 web 应用程序)

返回在指定的开始日期和结束日期之间交叉的指定日期部分边界的计数。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateDiff**(*DatePart*、开始*日期*和*结束*日期) 
  
**DateDiff**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |是指定所交叉边界类型的*起始日期*和*结束*日期的部分。 有关有效设置的列表, 请参阅 "备注" 部分。  <br/> |
| *StartDate*  <br/> |可以解析为日期/时间值的表达式。 *日期*参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
| *EndDate*  <br/> |可以解析为日期/时间值的表达式。 *日期*参数表达式、列表达式、用户定义的变量或字符串文本。  <br/> |
   
## <a name="remarks"></a>说明

下表列出了所有有效的*DatePart*参数。 
  
|***DatePart***|
|:-----|
|**year** <br/> |
|**结算** <br/> |
|**month** <br/> |
|**dayofyear** <br/> |
|**为期** <br/> |
|**周** <br/> |
|**七点** <br/> |
|**还要** <br/> |
|**第二个** <br/> |
|**加** <br/> |
   

