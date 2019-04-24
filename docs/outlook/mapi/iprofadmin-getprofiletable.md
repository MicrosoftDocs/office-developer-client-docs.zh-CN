---
title: IProfAdminGetProfileTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetProfileTable
api_type:
- COM
ms.assetid: cebccd2d-8215-486e-9964-7fc42412cec6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2db7dba67e7b71df6921ecd97189255a0ef7823a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309546"
---
# <a name="iprofadmingetprofiletable"></a>IProfAdmin::GetProfileTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对配置文件表 (包含所有可用配置文件的相关信息的表) 的访问权限。
  
```cpp
HRESULT GetProfileTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时始终为 NULL。
    
 _lppTable_
  
> 排除指向指向配置文件表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索配置文件表。
    
## <a name="remarks"></a>注解

**IProfAdmin:: GetProfileTable**方法提供对配置文件表的访问, 其中每个可用的配置文件在其中占一行。 每行中仅有两列: 配置文件的显示名称和指示是否为默认配置文件的标志。 
  
配置文件表中不包含已删除或正在使用但已标记为删除的配置文件。 配置文件表是静态的;后续的配置文件添加和删除不会反映在表中。 
  
如果不存在任何配置文件, **GetProfileTable**将返回一个包含零行的表。 
  
有关配置文件表的详细信息, 请参阅[profile Tables 表](profile-tables.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg  <br/> |CMainDlg:: OnShowProfiles  <br/> |MFCMAPI 使用**IProfAdmin:: GetProfileTable**方法获取要在新对话框中显示的配置文件表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

