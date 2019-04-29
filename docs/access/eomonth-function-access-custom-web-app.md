---
title: EOMonth 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: df98bcca-152b-49f2-b4e1-35d68008fb8f
description: 返回前一个月或指定的月数之前的最后一天。
ms.openlocfilehash: 87a837069be223fdd2f9c809d706782e0955e2aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437453"
---
# <a name="eomonth-function-access-custom-web-app"></a>EOMonth 函数 (Access 自定义 web 应用程序)

返回前一个月或指定的月数之前的最后一天。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **EOMonth**(*Date*、 *NumberOfMonth*) 
  
**EOMonth**包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Date*  <br/> |日期/时间格式或日期的可接受文本表示形式中的开始日期。  <br/> |
| *NumberOfMonth*  <br/> |表示*日期*之前或之后的月数的数字。  <br/> |
   
## <a name="remarks"></a>说明

如果*date*不是有效日期, 则**EOMonth**将返回一个错误。 
  
如果*date*加*NumberOfMonth*生成了无效日期, 则**EOMonth**将返回错误。 
  

