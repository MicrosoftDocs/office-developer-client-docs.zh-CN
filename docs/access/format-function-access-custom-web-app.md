---
title: Format 函数（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: 550fc235-f0b9-4d8e-805b-ce467821a8c9
description: 返回根据指定的模式进行格式化的值。
localization_priority: Priority
ms.openlocfilehash: 5331df30f276a7edd0571e9bf24c759d57ec6a54
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710389"
---
# <a name="format-function-access-custom-web-app"></a>Format 函数（Access 自定义 Web 应用）

返回根据指定的模式进行格式化的值。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Format** (*Expression*, *Format*) 
  
**Format** 函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Expression*  <br/> |要设置格式的受支持数据类型的表达式。  <br/> |
| *Format*  <br/> | 格式模式。 格式参数必须包含有效的格式字符串，作为标准格式字符串（例如，“C”或“D”）或日期和数字值的自定义字符的模式（例如，“MMMM dd、yyyy (dddd)”）。 有关详细信息，请参阅“备注”。  <br/> |
   
## <a name="remarks"></a>备注

对于 *Format* 参数，可以传递与以下任何模式匹配的字符串： 
  
- [标准数字格式字符串](https://msdn.microsoft.com/library/dwhawy9k%28v=vs.110%29.aspx)
    
- [自定义数字格式字符串](https://msdn.microsoft.com/library/0c899ak8%28v=vs.110%29.aspx)
    
- [标准日期和时间格式字符串](https://msdn.microsoft.com/library/az4se3k1%28v=vs.110%29.aspx)
    
- [自定义日期和时间格式字符串](https://msdn.microsoft.com/library/8kb3ddd4%28v=vs.110%29.aspx)
    
不能在 Access 2013 Web 应用的以下区域中使用 **Format** 函数： 
  
- 表级别的计算列
    
- UI 宏
    
- 视图中的表达式（例如，在窗体中）
    

