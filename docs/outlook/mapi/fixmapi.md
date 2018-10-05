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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383812"
---
# <a name="fixmapi"></a>FixMAPI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端上创建 mapi32.dll 当前副本的备份副本，计算机，并还原 mapi32.dll 与 MAPI 存根库，mapistub.dll。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |mapistub.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Windows  <br/> |
   
```cpp
DWORD STDAPICALLTYPE FixMAPI(void); 
```

## <a name="return-values"></a>返回值

如果函数成功，返回值为非零值。
  
如果函数失败，则返回的值为零。 若要获取扩展的错误的信息，请调用的 Microsoft Windows 软件开发工具包 (SDK) 函数，**[时出错](https://msdn.microsoft.com/library/ms679360.aspx)**。 
  
## <a name="remarks"></a>说明

 如果该文件标记为只读， **FixMAPI**不替换当前 mapi32.dll 文件。 
  
 如果在计算机上安装了 Microsoft Exchange Server **FixMAPI**不替换当前 mapi32.dll。 
  
当**FixMAPI** mapi32.dll 当前副本的备份副本的计算机上，它会将备份副本分配"mapi32.dll"不同的名称。 然后，它将定向专为备份复制到该程序集的后续呼叫。 
  
## <a name="see-also"></a>另请参阅



[KB 256946： 您可以收到程序冲突错误消息，启动 Outlook 2000 时](https://support.microsoft.com/kb/256946)
  
[KB 228457: Fixmapi.exe 工具的说明包含带有 Internet Explorer 5](https://support.microsoft.com/kb/228457)

