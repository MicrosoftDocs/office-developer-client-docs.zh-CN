---
title: SetProperty 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1e97dd95-23f6-4f49-b3b9-2c7261b3a70d
description: 您可以使用 SetProperty 操作设置视图上的控件的属性。
ms.openlocfilehash: 89ac2b10715d707d3b6ee09ee8ab915384c5acf5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773598"
---
# <a name="setproperty-macro-action-access-custom-web-app"></a>SetProperty 宏操作 （访问自定义 web 应用程序）

您可以使用**SetProperty**操作设置视图上的控件的属性。 
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="setting"></a>设置

**SetProperty**操作具有以下表中列出的参数。 
  
|**操作参数**|**说明**|
|:-----|:-----|
| _控件名称_ <br/> |键入您要为其设置属性值的控件的字段的名称。 将此参数留空将视图属性设置。  <br/> |
| _属性_ <br/> |选择您想要设置的属性。 请参阅**备注**部分中可以使用此操作设置的属性列表。  <br/> |
| _值_ <br/> |键入的值的属性设置为。 属性，其值为是或是否，使用 **-1** ， **0**表示否。  <br/> |
   
## <a name="remarks"></a>备注

您可以使用**SetProperty**操作设置控件的下列属性： 
  
- Caption
    
- 已启用
    
- 前景色
    
- 值
    
- Visible
    
如果为 ** *值* ** 参数输入的值无效，则不会发生错误，但 Access 可能会根据解释该参数的方式将属性更改为其他值。 
  

