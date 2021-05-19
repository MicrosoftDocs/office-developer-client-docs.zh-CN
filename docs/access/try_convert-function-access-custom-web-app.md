---
title: 'Try_Convert Function (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea514f19-4742-4eb4-823d-6f2494668106
description: 将值转换为指定的数据类型或返回 Null（如果转换无效）。
ms.openlocfilehash: 473d9063da46652afa88dc974cb4c4036e1c326c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410894"
---
# <a name="try_convert-function-access-custom-web-app"></a>Try_Convert Function (Access 自定义 Web 应用) 

将值转换为指定的数据类型或返回 Null（如果转换无效）。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Try_Convert (***数据类型，**表达式)* 
  
the **Try_Convert** function contains the following arguments. 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *DataType*  <br/> |要将数据类型转换到的 *表达式 。*  <br/> |
| *Expression*  <br/> |要转换的值。  <br/> |
   
## <a name="remarks"></a>备注

 **Try_Convert** 传递给它的值，并尝试将其转换为指定的  *数据类型*  。 如果转换 **成功，则** Try_Convert  *DataType*  返回值;如果发生错误，则返回 null。 但是，如果您请求明确不允许的转换，则 **Try_Convert失败并** 出现错误。 
  

