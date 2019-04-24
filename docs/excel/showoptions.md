---
title: ShowOptions
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 51acac58-ec39-488f-979c-1887dc2ab94b
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5b58b71dc4f2441448eb3e0dac2c3c5763675927
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310425"
---
# <a name="showoptions"></a>ShowOptions

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
显示一个模式对话框, 以收集用户的信息。 当用户单击 " **Excel 选项**" 对话框 (在 "**公式**" 部分下的 "**高级**" 类别中) 的 "**群集类型**" 框旁边的 "**选项**" 按钮时, 将调用此入口点。 群集连接器负责实现其自己的 "选项" 对话框界面以及将相关数据存储在注册表或其他地方。 选项是群集连接器的内部选项。 Excel 并不知道它们。 
  
```cpp
int ShowOptions(HWND hWndParent)
```

## <a name="parameters"></a>参数

_hWndParent_
  
> Excel 窗口的句柄。
    
## <a name="return-value"></a>返回值

如果显示对话框, 则为**xlHpcRetSuccess** ;如果未显示**xlHpcRetCallFailed** , 则为。 
  
## <a name="remarks"></a>注解

群集连接器可以使用此对话框从用户处获取信息 (如要使用哪个群集服务器)。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

