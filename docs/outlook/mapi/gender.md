---
title: Gender
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f60c65e3-b55f-cb68-746e-d0a8cd862d4d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 042216df309e98f35ed0ad71742e46300ebb06da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342579"
---
# <a name="gender"></a>Gender

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定邮件用户的性别的可能值。
  
## <a name="quick-info"></a>快速信息

```cpp
enum Gender { 
    genderMin = 0, 
    genderUnspecified = genderMin, 
    genderFemale, 
    genderMale, 
    genderCount, 
    genderMax = genderCount - 1 
}; 

```

## <a name="members"></a>成员

 _genderMin_
  
> 为性别支持的最小不同值数。
    
 _genderUnspecified_
  
> 不指定邮件用户的性别。
    
 _genderFemale_
  
> 邮件用户是女。
    
 _genderMale_
  
> 邮件用户是男。
    
 _genderCount_
  
> 性别支持的不同值的数量。
    
 _genderMax_
  
> 性别支持的最大不同值数。
    
## <a name="see-also"></a>另请参阅



[PidTagGender 规范属性](pidtaggender-canonical-property.md)

