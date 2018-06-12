---
title: ShowOptions
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 51acac58-ec39-488f-979c-1887dc2ab94b
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: dbf6f0f50e9f7fa988e83f3b58012e9deac13eac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773814"
---
# <a name="showoptions"></a>ShowOptions

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
显示一个模式对话框，以从用户处收集信息。 用户单击选定的群集连接器 （在**公式**部分下的**高级**类别中） 在**Excel 选项**对话框**群集类型**框旁边的**选项**按钮时调用此入口点。 群集连接器是负责实现自己选项对话框接口并存储在注册表中或其他位置的相关的数据。 选项都是内部人员到群集连接器。 Excel 不了解它们。 
  
```cpp
int ShowOptions(HWND hWndParent)
```

## <a name="parameters"></a>参数

_hWndParent_
  
> Excel 窗口的句柄。
    
## <a name="return-value"></a>返回值

**xlHpcRetSuccess**如果对话框已显示;**xlHpcRetCallFailed**如果它不显示。 
  
## <a name="remarks"></a>备注

群集连接器可以使用此对话框中获取信息，例如，若要使用，从用户哪些群集服务器。
  
## <a name="see-also"></a>另请参阅

- [Excel 群集连接器函数](excel-cluster-connector-functions.md)

