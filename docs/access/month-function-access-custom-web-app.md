---
title: 'Month 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5df43594-a434-4fb7-8109-e5cf0401ae09
description: 返回一个整数，该整数表示指定日期的月份。
ms.openlocfilehash: 0ca7059a2fd6dad1f9790ad6f4eafe7affa014dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411489"
---
# <a name="month-function-access-custom-web-app"></a>Month 函数 (Access 自定义 Web 应用) 

返回一个整数，该整数表示指定日期的月份。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Month** (*Date*)  
  
**Month** 函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Date*  <br/> |可以解析为"日期/时间"值的表达式。  <br/> |
   
## <a name="remarks"></a>备注

 **Month** 返回的值与 **DatePart** (月， date) 。 
  
如果  *Date*  仅包含时间部分，则返回值为 1，即基月。 
  

