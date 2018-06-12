---
title: IOlkEnumGetNext
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b387f896-c213-fc07-a12a-33917e620837
description: 获取枚举中的下一个帐户。
ms.openlocfilehash: 496a4d787916d051c051b3a19a7113d9d50c6fe7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774376"
---
# <a name="iolkenumgetnext"></a>IOlkEnum::GetNext

获取枚举中的下一个帐户。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkEnum](iolkenum.md)。
  
```cpp
HRESULT IOlkEnum:: GetNext( 
    LPUNKNOWN *ppunk 
);

```

## <a name="parameters"></a>参数

_ppunk_
  
> [in]指向客户端可以查询以获取[IOlkAccount](iolkaccount.md)接口的**IUnknown**接口的指针。 
    
## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |调用成功。  <br/> |
|S_FALSE  <br/> |将枚举器重已达到结束。  <br/> |
   
## <a name="remarks"></a>备注

从**IUnknown**继承*ppunk*由指定的接口。 客户端可以查询此接口 （使用**IUnknown::QueryInterface**） 以获取指向**IOlkAccount**接口，并获取或设置为此帐户的信息。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md) 
- [IOlkEnum::GetCount](iolkenum-getcount.md)  
- [IOlkEnum::Reset](iolkenum-reset.md) 
- [IOlkEnum::Skip](iolkenum-skip.md)

