---
title: 当 Outlook 处于缓存 Exchange 模式下时, 打开远程服务器上的存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: cf01eab7-164d-c3b3-8bb0-9281e2119bc5
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 419c9ae734e8b58d0958970e7127b94d220b8382
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417817"
---
# <a name="open-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a>当 Outlook 处于缓存 Exchange 模式下时, 打开远程服务器上的存储区

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含 c + + 中的代码示例, 说明在 microsoft outlook 2010 或 microsoft outlook 2013 处于缓存 Exchange 模式下时, 如何使用**MDB_ONLINE**标志打开远程服务器上的邮件存储区。 
  
缓存 Exchange 模式允许 outlook 2010 和 outlook 2013 使用用户邮箱的本地副本, 而 outlook 2010 或 outlook 2013 维护与远程 Exchange 服务器上的用户邮箱远程副本的联机连接。 当 outlook 2010 或 outlook 2013 在缓存 Exchange 模式下运行时, 默认情况下, 登录到同一会话的任何 MAPI 解决方案也将连接到缓存的邮件存储区。 访问的任何数据和所做的任何更改都将针对邮箱的本地副本进行。
  
客户端或服务提供程序可以通过在调用[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)时为*ulFlags*参数中的**MDB_ONLINE**设置重写与本地邮件存储区的连接并在远程服务器上打开存储区。 在该会话的远程服务器上成功打开存储后, 您可以使用[IMAPISession:: OpenEntry](imapisession-openentry.md)打开远程存储上的项目或文件夹。 
  
无法同时在缓存模式和非缓存模式下打开同一 MAPI 会话中的 Exchange 存储。 如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。
  
下面的代码示例演示如何使用*ulFlags*参数中设置的**MDB_ONLINE**标志调用**IMAPISession:: OpenMsgStore** , 以打开远程服务器上的默认存储区。 
  
```cpp
HRESULT HrRemoteMessageStore( 
    LPMAPISESSION lpMAPISession, 
    LPMDB* lppMDB) 
{ 
    HRESULT hRes = S_OK; 
    LPMAPITABLE pStoresTbl = NULL; 
    SRestriction sres = {0}; 
    SPropValue spv = {0}; 
    LPSRowSet pRow = NULL; 
    LPMDB lpTempMDB = NULL; 
    enum {EID,NUM_COLS}; 
    static SizedSPropTagArray(NUM_COLS,sptCols) = {NUM_COLS, 
        PR_ENTRYID, 
    }; 
 
    //Obtain the table of all the message stores that are available 
    hRes = lpMAPISession-&gt;GetMsgStoresTable(0, &amp;pStoresTbl); 
     
    if (SUCCEEDED(hRes) &amp;&amp; pStoresTbl) 
    { 
        //Set up restrictions for the default store 
        sres.rt = RES_PROPERTY;                                  //Comparing a property 
        sres.res.resProperty.relop = RELOP_EQ;                   //Testing equality 
        sres.res.resProperty.ulPropTag = PR_DEFAULT_STORE;       //Tag to compare 
        sres.res.resProperty.lpProp = &amp;spv;                      //Prop tag and value to compare against 
     
        spv.ulPropTag = PR_DEFAULT_STORE;                        //Tag type 
        spv.Value.b   = TRUE;                                    //Tag value 
     
        //Convert the table to an array that can be stepped through 
        //Only one message store should have PR_DEFAULT_STORE set to true, so that only one will be returned 
        hRes = HrQueryAllRows( 
            pStoresTbl,                                          //Table to query 
            (LPSPropTagArray) &amp;sptCols,                          //Which columns to obtain 
            &amp;sres,                                               //Restriction to use 
            NULL,                                                //No sort order 
            0,                                                   //Max number of rows (0 means no limit) 
            &amp;pRow);                                              //Array to return 
 
        if (SUCCEEDED(hRes) &amp;&amp; pRow &amp;&amp; pRow-&gt;cRows) 
        {     
            //Open the first returned (default) message store 
            hRes = lpMAPISession-&gt;OpenMsgStore( 
                NULL,                                                //Window handle for dialogs 
                pRow-&gt;aRow[0].lpProps[EID].Value.bin.cb,             //size and... 
                (LPENTRYID)pRow-&gt;aRow[0].lpProps[EID].Value.bin.lpb, //value of entry to open 
                NULL,                                                //Use default interface (IMsgStore) to open store 
                MAPI_BEST_ACCESS | MDB_ONLINE,                       //Flags 
                &amp;lpTempMDB);                                         //Pointer to put the store in 
            if (SUCCEEDED(hRes) &amp;&amp; lppMDB) lppMDB* = lpTempMDB; 
        } 
    } 
    FreeProws(pRow); 
    if (pStoresTbl) pStoresTbl-&gt;Release(); 
 
    return hRes; 
}

```

## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [MAPI 常量](mapi-constants.md)
- [当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)

