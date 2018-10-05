---
title: 创建简单的邮件项目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bbf99c4b-3008-4475-a60a-648eaed59d01
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8b7afa8f3c04cb479906f721db8de90e8cf66f11
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401452"
---
# <a name="create-a-simple-mail-item"></a><span data-ttu-id="e2b67-103">创建简单的邮件项目</span><span class="sxs-lookup"><span data-stu-id="e2b67-103">Create a simple mail item</span></span>
  
<span data-ttu-id="e2b67-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2b67-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2b67-105">可以使用 MAPI 创建和发送一条消息，请求已读的回执。</span><span class="sxs-lookup"><span data-stu-id="e2b67-105">MAPI can be used to create and send a message that requests a read receipt.</span></span> <span data-ttu-id="e2b67-106">已读的回执请求时，在邮件系统生成，并返回阅读的报告发件人在收件人打开邮件时会。</span><span class="sxs-lookup"><span data-stu-id="e2b67-106">When a read receipt is requested, the messaging system generates and returns a read report to the sender when the recipient opens the message.</span></span>
  
<span data-ttu-id="e2b67-107">有关如何下载、 查看和 MFCMAPI 应用程序和此主题中所述的 CreateOutlookItemsAddin 项目从运行代码的信息，请参阅[安装使用本节中的示例](how-to-install-the-samples-used-in-this-section.md)。</span><span class="sxs-lookup"><span data-stu-id="e2b67-107">For information about how to download, view, and run the code from the MFCMAPI application and CreateOutlookItemsAddin project referenced in this topic, see [Install the Samples Used in This Section](how-to-install-the-samples-used-in-this-section.md).</span></span>


### <a name="to-create-and-send-a-message-requesting-a-read-receipt"></a><span data-ttu-id="e2b67-108">若要创建并发送已读的回执请求邮件</span><span class="sxs-lookup"><span data-stu-id="e2b67-108">To create and send a message requesting a read receipt</span></span>

1. <span data-ttu-id="e2b67-109">创建传出邮件。</span><span class="sxs-lookup"><span data-stu-id="e2b67-109">Create an outgoing message.</span></span> <span data-ttu-id="e2b67-110">有关如何创建传出邮件的信息，请参阅[处理传出邮件](handling-an-outgoing-message.md)。</span><span class="sxs-lookup"><span data-stu-id="e2b67-110">For information about how to create an outgoing message, see [Handling an Outgoing Message](handling-an-outgoing-message.md).</span></span>
    
2. <span data-ttu-id="e2b67-111">添加**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性，并将其设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="e2b67-111">Add the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property and set it to **true**.</span></span>
    
3. <span data-ttu-id="e2b67-112">添加**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e2b67-112">Add the **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property.</span></span>
    
4. <span data-ttu-id="e2b67-113">添加**PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e2b67-113">Add the **PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) property.</span></span>
    
5. <span data-ttu-id="e2b67-114">通过调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="e2b67-114">Send the message by calling the [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> 
    
<span data-ttu-id="e2b67-115">`AddMail` CreateOutlookItemsAddin 项目的 Mails.cpp 源文件中的函数演示了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e2b67-115">The  `AddMail` function in the Mails.cpp source file of the CreateOutlookItemsAddin project demonstrates these steps.</span></span> <span data-ttu-id="e2b67-116">`AddMail`函数采用参数从时单击**添加邮件**命令 MFCMAPI 示例应用程序中的**加载项**菜单上显示**添加邮件**对话框。</span><span class="sxs-lookup"><span data-stu-id="e2b67-116">The  `AddMail` function takes parameters from the **Add Mail** dialog box that is displayed when you click the **Add Mail** command on the **Addins** menu in the MFCMAPI sample application.</span></span> <span data-ttu-id="e2b67-117">`DisplayAddMailDialog`中 Mails.cpp 函数显示对话框，并将值传递从对话框到`AddMail`函数。</span><span class="sxs-lookup"><span data-stu-id="e2b67-117">The  `DisplayAddMailDialog` function in Mails.cpp displays the dialog box and passes the values from the dialog box to the  `AddMail` function.</span></span> <span data-ttu-id="e2b67-118">`DisplayAddMailDialog`函数直接与创建邮件项目使用 MAPI，因此它不在此处列出是无关。</span><span class="sxs-lookup"><span data-stu-id="e2b67-118">The  `DisplayAddMailDialog` function does not relate directly to creating a mail item using MAPI, so it is not listed here.</span></span> <span data-ttu-id="e2b67-119">`AddMail`下面列出了函数。</span><span class="sxs-lookup"><span data-stu-id="e2b67-119">The  `AddMail` function is listed below.</span></span> 
  
<span data-ttu-id="e2b67-120">请注意， _lpFolder_参数传递给`AddMail`方法是指向[IMAPIFolder](imapifolderimapicontainer.md)接口，表示将在其中创建新邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2b67-120">Note that the  _lpFolder_ parameter passed to the  `AddMail` method is a pointer to an [IMAPIFolder](imapifolderimapicontainer.md) interface that represents the folder where the new message will be created.</span></span> <span data-ttu-id="e2b67-121">给定_lpFolder_参数值，该值代表**IMAPIFolder**接口，代码调用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e2b67-121">Given the  _lpFolder_ parameter that represents an **IMAPIFolder** interface, the code calls the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="e2b67-122">**CreateMessage**方法返回成功代码和指针是指向[IMessage: IMAPIProp](imessageimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e2b67-122">The **CreateMessage** method returns a success code and a pointer to a pointer to an [IMessage : IMAPIProp](imessageimapiprop.md) interface.</span></span> 

<span data-ttu-id="e2b67-123">大多数的`AddMail`的函数代码处理属性设置在调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法的准备工作。</span><span class="sxs-lookup"><span data-stu-id="e2b67-123">Most of the  `AddMail` function code handles the work of setting properties in preparation for calling the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="e2b67-124">如果对**SetProps**方法的调用成功，对[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法的调用将应用到存储的更改，并创建一个新的邮件项目。</span><span class="sxs-lookup"><span data-stu-id="e2b67-124">If the call to the **SetProps** method succeeds, a call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method commits the changes to the store and creates a new mail item.</span></span> <span data-ttu-id="e2b67-125">然后，如果请求， [IMessage::SubmitMessage](imessage-submitmessage.md)方法调用发送消息。</span><span class="sxs-lookup"><span data-stu-id="e2b67-125">Then, if requested, the [IMessage::SubmitMessage](imessage-submitmessage.md) method is called to send the message.</span></span> 
  
<span data-ttu-id="e2b67-126">`AddMail`函数使用两个帮助程序函数来构建**PR_CONVERSATION_INDEX**和**PR_REPORT_TAG**属性的值：`BuildConversationIndex`和`AddReportTag`函数。</span><span class="sxs-lookup"><span data-stu-id="e2b67-126">The  `AddMail` function uses two helper functions to build values for the **PR_CONVERSATION_INDEX** and **PR_REPORT_TAG** properties: the  `BuildConversationIndex` and  `AddReportTag` functions.</span></span> <span data-ttu-id="e2b67-127">`BuildConversationIndex`函数，位于 CreateOutlookItemsAddin.cpp，执行内置的 MAPI [ScCreateConversationIndex](sccreateconversationindex.md)函数执行时父对话索引不传递给它的同一工作。</span><span class="sxs-lookup"><span data-stu-id="e2b67-127">The  `BuildConversationIndex` function, located in CreateOutlookItemsAddin.cpp, does the same work that the built-in MAPI [ScCreateConversationIndex](sccreateconversationindex.md) function does when a parent conversation index is not passed to it.</span></span> <span data-ttu-id="e2b67-128">[PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)中介绍了这些函数生成对话索引缓冲区的格式。</span><span class="sxs-lookup"><span data-stu-id="e2b67-128">The format of the conversation index buffer that these functions generate is documented in [PidTagConversationIndex Canonical Property](pidtagconversationindex-canonical-property.md).</span></span> 

<span data-ttu-id="e2b67-129">`AddReportTag`函数，位于 Mails.cpp，又调用`BuildReportTag`函数构建**PR_REPORT_TAG**属性结构。</span><span class="sxs-lookup"><span data-stu-id="e2b67-129">The  `AddReportTag` function, located in Mails.cpp, in turn calls the  `BuildReportTag` function to build a structure for the **PR_REPORT_TAG** property.</span></span> <span data-ttu-id="e2b67-130">有关结构的信息的`BuildReportTag`函数生成，请参阅[PidTagReportTag 规范属性](pidtagreporttag-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="e2b67-130">For information about the structure that the  `BuildReportTag` function builds, see [PidTagReportTag Canonical Property](pidtagreporttag-canonical-property.md).</span></span>
  
<span data-ttu-id="e2b67-131">下面是的完整列表`AddMail`函数。</span><span class="sxs-lookup"><span data-stu-id="e2b67-131">The following is the complete listing of the  `AddMail` function.</span></span> 
  
```cpp
HRESULT AddMail(LPMAPISESSION lpMAPISession,
            LPMAPIFOLDER lpFolder,
            LPWSTR szSubject, // PR_SUBJECT_W, PR_CONVERSATION_TOPIC
            LPWSTR szBody, // PR_BODY_W
            LPWSTR szRecipientName, // Recipient table
            BOOL bHighImportance, // PR_IMPORTANCE
            BOOL bReadReceipt, // PR_READ_RECEIPT_REQUESTED
            BOOL bSubmit,
            BOOL bDeleteAfterSubmit)
{
   if (!lpFolder) return MAPI_E_INVALID_PARAMETER;
   HRESULT hRes = S_OK;
   LPMESSAGE lpMessage = 0;
   // Create a message and set its properties
   hRes = lpFolder->CreateMessage(0,
      0,
      &lpMessage);
   if (SUCCEEDED(hRes))
   {
      // Because the properties to be set are known in advance, 
      // most of the structures involved can be statically declared 
      // to minimize expensive MAPIAllocateBuffer calls.
      SPropValue spvProps[NUM_PROPS] = {0};
      spvProps[p_PR_MESSAGE_CLASS_W].ulPropTag          = PR_MESSAGE_CLASS_W;
      spvProps[p_PR_ICON_INDEX].ulPropTag                 = PR_ICON_INDEX;
      spvProps[p_PR_SUBJECT_W].ulPropTag                = PR_SUBJECT_W;
      spvProps[p_PR_CONVERSATION_TOPIC_W].ulPropTag     = PR_CONVERSATION_TOPIC_W;
      spvProps[p_PR_BODY_W].ulPropTag                   = PR_BODY_W;
      spvProps[p_PR_IMPORTANCE].ulPropTag               = PR_IMPORTANCE;
      spvProps[p_PR_READ_RECEIPT_REQUESTED].ulPropTag   = PR_READ_RECEIPT_REQUESTED;
      spvProps[p_PR_MESSAGE_FLAGS].ulPropTag             = PR_MESSAGE_FLAGS;
      spvProps[p_PR_MSG_EDITOR_FORMAT].ulPropTag         = PR_MSG_EDITOR_FORMAT;
      spvProps[p_PR_MESSAGE_LOCALE_ID].ulPropTag         = PR_MESSAGE_LOCALE_ID;
      spvProps[p_PR_INETMAIL_OVERRIDE_FORMAT].ulPropTag = PR_INETMAIL_OVERRIDE_FORMAT;
      spvProps[p_PR_DELETE_AFTER_SUBMIT].ulPropTag      = PR_DELETE_AFTER_SUBMIT;
      spvProps[p_PR_INTERNET_CPID].ulPropTag            = PR_INTERNET_CPID;
      spvProps[p_PR_CONVERSATION_INDEX].ulPropTag         = PR_CONVERSATION_INDEX;
      spvProps[p_PR_MESSAGE_CLASS_W].Value.lpszW = L"IPM.Note";
      spvProps[p_PR_ICON_INDEX].Value.l = 0x103; // Unsent Mail
      spvProps[p_PR_SUBJECT_W].Value.lpszW = szSubject;
      spvProps[p_PR_CONVERSATION_TOPIC_W].Value.lpszW = szSubject;
      spvProps[p_PR_BODY_W].Value.lpszW = szBody;
      spvProps[p_PR_IMPORTANCE].Value.l = bHighImportance?IMPORTANCE_HIGH:IMPORTANCE_NORMAL;
      spvProps[p_PR_READ_RECEIPT_REQUESTED].Value.b = bReadReceipt?true:false;
      spvProps[p_PR_MESSAGE_FLAGS].Value.l = MSGFLAG_UNSENT;
      spvProps[p_PR_MSG_EDITOR_FORMAT].Value.l = EDITOR_FORMAT_PLAINTEXT;
      spvProps[p_PR_MESSAGE_LOCALE_ID].Value.l = 1033; // (en-us)
      spvProps[p_PR_INETMAIL_OVERRIDE_FORMAT].Value.l = NULL; // Mail system chooses default encoding scheme
      spvProps[p_PR_DELETE_AFTER_SUBMIT].Value.b = bDeleteAfterSubmit?true:false;
      spvProps[p_PR_INTERNET_CPID].Value.l = cpidASCII;
      hRes = BuildConversationIndex(
         &spvProps[p_PR_CONVERSATION_INDEX].Value.bin.cb,
         &spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb);
      if (SUCCEEDED(hRes))
      {
         hRes = lpMessage->SetProps(NUM_PROPS, spvProps, NULL);
         if (SUCCEEDED(hRes))
         {
            hRes = AddRecipient(lpMAPISession,
               lpMessage,
               MAPI_TO,
               szRecipientName);
            AddInLog(true,L"CallMenu: AddRecipient - returned hRes = 0x%08X\n",hRes);
            if (SUCCEEDED(hRes))
            {
               if (bReadReceipt)
               {
                  hRes = AddReportTag(lpMessage);
               }
               if (SUCCEEDED(hRes))
               {
                  hRes = lpMessage->SaveChanges(KEEP_OPEN_READWRITE);
                  if (SUCCEEDED(hRes) && bSubmit)
                  {
                     hRes = lpMessage->SubmitMessage(NULL);
                  }
               }
            }
         }
      }
      if (spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb)
         delete[] spvProps[p_PR_CONVERSATION_INDEX].Value.bin.lpb;
   }
   if (lpMessage) lpMessage->Release();
   return hRes;
}
```

## <a name="see-also"></a><span data-ttu-id="e2b67-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2b67-132">See also</span></span>

- [<span data-ttu-id="e2b67-133">使用 MAPI 创建 Outlook 2007 项</span><span class="sxs-lookup"><span data-stu-id="e2b67-133">Using MAPI to Create Outlook 2007 Items</span></span>](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

