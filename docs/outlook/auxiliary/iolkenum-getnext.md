---
title: IOlkEnumGetNext
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b387f896-c213-fc07-a12a-33917e620837
description: 获取枚举器中的下一个帐户。
ms.openlocfilehash: e2ad98f7d7e71bd91d48b3824423e305baab429a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405987"
---
# <a name="iolkenumgetnext"></a>IOlkEnum::GetNext

获取枚举器中的下一个帐户。
  
## <a name="quick-info"></a>快速信息

请参阅 [IOlkEnum](iolkenum.md)。
  
```cpp
HRESULT IOlkEnum:: GetNext( 
    LPUNKNOWN *ppunk 
);

```

## <a name="parameters"></a>参数

_ppunk_
  
> [in]指向客户端可查询以获取 [IOlkAccount](iolkaccount.md)接口的 **IUnknown** 接口的指针。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|S_FALSE  <br/> |枚举器已到达末尾。  <br/> |
   
## <a name="remarks"></a>备注

*ppunk* 指定的接口继承自 **IUnknown**。 客户端可以使用 **IUnknown：：QueryInterface** (查询此接口) 以获取 **指向 IOlkAccount** 接口的指针，并获取或设置此帐户的信息。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkEnum::GetCount](iolkenum-getcount.md)  
- [IOlkEnum::Reset](iolkenum-reset.md) 
- [IOlkEnum::Skip](iolkenum-skip.md)

