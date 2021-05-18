---
title: ShowOptions
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 51acac58-ec39-488f-979c-1887dc2ab94b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5b58b71dc4f2441448eb3e0dac2c3c5763675927
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407695"
---
# <a name="showoptions"></a>ShowOptions

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
显示从用户收集信息的模式对话框。 当用户单击"公式"部分下"高级"类别中 **" ("Excel** 选项"对话框中所选群集连接器的"群集类型"框旁边的"选项"按钮时，) 将调用此入口点。   群集连接器负责实现自己的选项对话框接口，以及将相关的数据存储在注册表或其他地方。 选项在群集连接器内部。 Excel他们。 
  
```cpp
int ShowOptions(HWND hWndParent)
```

## <a name="parameters"></a>参数

_hWndParent_
  
> 窗口的Excel句柄。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess（** 如果显示对话框）; **xlHpcRetCallFailed（** 如果未显示）。 
  
## <a name="remarks"></a>备注

群集连接器可以使用此对话框从用户获取信息，例如要使用哪些群集服务器。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

