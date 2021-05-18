---
title: 打开通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79e0bc93-f37d-4f6a-beed-7519d01e0056
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6d1a7e8e1d9debd7eb715bbe4958657c000f1e6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404545"
---
# <a name="opening-the-address-book"></a>打开通讯簿

**适用于**：Outlook 2013 | Outlook 2016 
  
调用 [IMAPISession：：OpenAddressBook](imapisession-openaddressbook.md) 以打开集成通讯簿并检索到 MAPI [IAddrBook ： IMAPIProp 接口的](iaddrbookimapiprop.md) 指针。 **IAddrBook** 接口的方法可用于访问配置文件中每个通讯簿提供程序的所有容器中的条目。 
  
**OpenAddressBook** 可能会返回警告MAPI_W_ERRORS_RETURNED，以指示一个或多个通讯簿提供程序出现问题。 交互式客户端应调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 以检索其他错误信息，并首次调用 **OpenAddressBook** 时显示返回的信息，并返回警告。 
  
非交互客户端应忽略警告并继续操作，就像方法成功一样。 返回 **的 IAddrBook** 接口有效，无论配置文件中是否正在运行所有、部分或没有任何通讯簿提供程序。 因此，交互和非交互客户端必须始终记住在会话结束时释放 **IAddrBook** 指针。 
  

