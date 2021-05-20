---
title: 'SetProperty 宏操作 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1e97dd95-23f6-4f49-b3b9-2c7261b3a70d
description: 可以使用 SetProperty 操作为视图上的控件设置属性。
ms.openlocfilehash: 1876be32606d66e0570c9e69206a508b8888b157
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438027"
---
# <a name="setproperty-macro-action-access-custom-web-app"></a>SetProperty 宏操作 (Access 自定义 Web 应用) 

可以使用 **SetProperty** 操作为视图上的控件设置属性。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**SetProperty** 操作具有下表中列出的参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
| _控件名称_ <br/> |请键入要为其设置属性值的字段或控件的名称。 将此参数留空可设置视图的属性。  <br/> |
| _Property_ <br/> |请选择要设置的属性。有关可以使用此操作设置的属性的列表，请参阅本文的 **说明** 部分。<br/> |
| _值_ <br/> |请键入要设置的属性值。对于值为“是”或“否”的属性，使用 **-1** 代表“是”，**0** 代表“否”。<br/> |
   
## <a name="remarks"></a>备注

可以使用 **SetProperty** 操作设置控件的以下属性： 
  
- Caption
    
- 已启用
    
- ForeColor
    
- 值
    
- Visible
    
如果为 ** *值* ** 参数输入的值无效，则不会发生错误，但 Access 可能会根据解释该参数的方式将属性更改为其他值。 
  

