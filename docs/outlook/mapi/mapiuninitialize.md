---
title: MAPIUninitialize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIUninitialize
api_type:
- HeaderDef
ms.assetid: 0f4e54dc-80e5-49a7-9703-0225d8133492
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f7339588bcc6815545e7341eafffe9cf001c1d76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408521"
---
# <a name="mapiuninitialize"></a>MAPIUninitialize

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
递减 MAPI DLL 的引用计数、清除和删除每个实例的全局数据。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
void MAPIUninitialize ( void );
```

## <a name="parameters"></a>参数

无 
  
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

客户端应用程序调用**MAPIUninitialize**函数来结束它与 MAPI 的交互, 并在调用[MAPIInitialize](mapiinitialize.md)函数时开始。 在调用**MAPIUninitialize**后, 客户端不能发出其他 MAPI 调用。 
  
 **MAPIUninitialize**递减引用计数, 相应的**MAPIInitialize**函数将递增引用计数。 因此, 对一个函数的调用次数必须等于对另一个函数的调用次数。 
  
> [!NOTE]
> 无法从 Win32 **DllMain**函数或任何其他创建或终止线程的函数中调用**MAPIInitialize**或**MAPIUninitialize** 。 有关详细信息, 请参阅[使用线程安全对象](using-thread-safe-objects.md)。 
  

