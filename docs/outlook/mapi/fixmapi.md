---
title: FixMAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 32676003-ba32-886f-1185-4760cb0e30e3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2aeca1a65a859ac9502995a463bc4869609bcd15
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334959"
---
# <a name="fixmapi"></a>FixMAPI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在客户端计算机上创建当前 mapi32.dll 副本的备份副本，并还原mapi32.dll MAPI 存根库mapistub.dll。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |mapistub.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Windows  <br/> |
   
```cpp
DWORD STDAPICALLTYPE FixMAPI(void); 
```

## <a name="return-values"></a>返回值

如果函数成功，则返回值为非零值。
  
如果函数失败，则返回值为 0。 若要获取扩展的错误信息，请调用 Microsoft Windows Software Development Kit (SDK) 函数 **[GetLastError](https://msdn.microsoft.com/library/ms679360.aspx)**。 
  
## <a name="remarks"></a>备注

 **FixMAPI** 不会替换当前mapi32.dll文件，如果该文件标记为只读。 
  
 **FixMAPI** 不会替换当前mapi32.dll如果Microsoft Exchange Server安装当前服务器。 
  
当 **FixMAPI** 在计算机上创建当前 mapi32.dll 副本的备份副本时，它会为备份副本分配一个不同于"mapi32.dll"的名称。 然后，它将针对该程序集的后续调用引导到备份副本。 
  
## <a name="see-also"></a>另请参阅



[KB 256946：在启动 2000 时收到Outlook错误消息](https://support.microsoft.com/kb/256946)
  
[KB 228457：Fixmapi.exe工具的说明 5 Internet Explorer 5](https://support.microsoft.com/kb/228457)

