---
title: DateDiff 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1c58ee87-0f57-4643-be4d-62da815df705
description: 返回指定的日期部分边界删除线之间的指定的开始日期和结束日期的计数。
ms.openlocfilehash: fe898ec5eb59cb341250cb0c0e2e35bc55d37eb3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773461"
---
# <a name="datediff-function-access-custom-web-app"></a>DateDiff 函数 （访问自定义 web 应用程序）

返回指定的日期部分边界删除线之间的指定的开始日期和结束日期的计数。
  
> [!NOTE]
> 本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。* > 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateDiff**(*DatePart*， *StartDate*， *EndDate*) 
  
**DateDiff**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DatePart*  <br/> |*StartDate*和*EndDate* ，指定的边界删除线类型的一部分。 引用有效设置列表的备注部分。  <br/> |
| *StartDate*  <br/> |一个可解析为日期/时间值的表达式。 *日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。  <br/> |
| *EndDate*  <br/> |一个可解析为日期/时间值的表达式。 *日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。  <br/> |
   
## <a name="remarks"></a>说明

下表列出了所有有效的*日期部分*参数。 
  
|***DatePart***|
|:-----|
|**year** <br/> |
|**季度** <br/> |
|**month** <br/> |
|**dayofyear** <br/> |
|**一天** <br/> |
|**周** <br/> |
|**小时** <br/> |
|**分钟** <br/> |
|**第二个** <br/> |
|**毫秒** <br/> |
   

