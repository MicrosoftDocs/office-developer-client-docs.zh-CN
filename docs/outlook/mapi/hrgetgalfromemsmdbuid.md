---
title: HrGetGALFromEmsmdbUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9b824e70-ed9a-490c-b777-8902a793fece
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5db1b45f42365837d7b0e7af91f859f221ff687b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775165"
---
# <a name="hrgetgalfromemsmdbuid"></a>HrGetGALFromEmsmdbUID

  
  
**适用于**： Outlook 
  
返回标识_pEmsmdbUID_的 Exchange 服务的全局通讯簿条目标识符。 应使用[MAPIFreeBuffer](mapifreebuffer.md)释放返回的项标识符。
  
|||
|:-----|:-----|
|头文件：  <br/> |abhelp.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrGetGALFromEmsmdbUID(
  LPMAPISESSION pSess,
  LPADRBOOK lpAdrBook,
  const MAPIUID * pEmsmdbUID,
  ULONG * lpcbeid,
  LPENTRYID * lppeid
);
```

## <a name="parameters"></a>参数

 _pSess_
  
> [in]登录 IMAPISession。 它不能为 NULL。
    
 _pAddrBook_
  
> [in]通讯簿用于打开的项标识符。 它不能为 NULL。
    
 _pEmsmdbUID_
  
> [in]标识要检索的 Exchange 服务 GAL **emsmdbUID**指向的指针。 如果_pEmsmdbUID_为 NULL 或零 UID，此函数获取旧 GAL 的 Exchange 服务。 
    
 _lpcbeid_
  
> [输出]一个指向全局地址列表的项标识符的字节数。
    
 _lppeid_
  
> [输出]一个指向全局地址列表的项标识符。 应使用[MAPIFreeBuffer](mapifreebuffer.md)释放这。
    

