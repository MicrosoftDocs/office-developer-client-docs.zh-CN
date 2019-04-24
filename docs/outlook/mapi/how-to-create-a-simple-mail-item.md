---
title: 创建简单邮件项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bbf99c4b-3008-4475-a60a-648eaed59d01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8b7afa8f3c04cb479906f721db8de90e8cf66f11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345191"
---
# <a name="create-a-simple-mail-item"></a><span data-ttu-id="1e4ad-103">创建简单邮件项</span><span class="sxs-lookup"><span data-stu-id="1e4ad-103">Create a simple mail item</span></span>
  
<span data-ttu-id="1e4ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1e4ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1e4ad-105">MAPI 可用于创建和发送请求已读回执的邮件。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-105">MAPI can be used to create and send a message that requests a read receipt.</span></span> <span data-ttu-id="1e4ad-106">当请求 "已读" 回执时, 邮件系统会生成收件人打开邮件时, 并向发件人返回阅读报告。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-106">When a read receipt is requested, the messaging system generates and returns a read report to the sender when the recipient opens the message.</span></span>
  
<span data-ttu-id="1e4ad-107">有关如何从本主题所引用的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目中下载、查看和运行代码的信息, 请参阅[Install the 本节中使用的示例](how-to-install-the-samples-used-in-this-section.md)。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-107">For information about how to download, view, and run the code from the MFCMAPI application and CreateOutlookItemsAddin project referenced in this topic, see [Install the Samples Used in This Section](how-to-install-the-samples-used-in-this-section.md).</span></span>


### <a name="to-create-and-send-a-message-requesting-a-read-receipt"></a><span data-ttu-id="1e4ad-108">创建和发送请求已读回执的邮件</span><span class="sxs-lookup"><span data-stu-id="1e4ad-108">To create and send a message requesting a read receipt</span></span>

1. <span data-ttu-id="1e4ad-109">创建传出邮件。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-109">Create an outgoing message.</span></span> <span data-ttu-id="1e4ad-110">有关如何创建传出邮件的信息, 请参阅[处理传出邮件](handling-an-outgoing-message.md)。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-110">For information about how to create an outgoing message, see [Handling an Outgoing Message](handling-an-outgoing-message.md).</span></span>
    
2. <span data-ttu-id="1e4ad-111">添加**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性并将其设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-111">Add the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property and set it to **true**.</span></span>
    
3. <span data-ttu-id="1e4ad-112">添加**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-112">Add the **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property.</span></span>
    
4. <span data-ttu-id="1e4ad-113">添加**PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-113">Add the **PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) property.</span></span>
    
5. <span data-ttu-id="1e4ad-114">通过调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法发送邮件。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-114">Send the message by calling the [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> 
    
<span data-ttu-id="1e4ad-115">CreateOutlookItemsAddin `AddMail`项目的邮件 .cpp 源文件中的函数演示这些步骤。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-115">The  `AddMail` function in the Mails.cpp source file of the CreateOutlookItemsAddin project demonstrates these steps.</span></span> <span data-ttu-id="1e4ad-116">`AddMail`函数采用 "**添加邮件**" 对话框中的参数, 当您单击 MFCMAPI 示例应用程序中的 " **Addins** " 菜单上的 "**添加邮件**" 命令时, 将显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-116">The  `AddMail` function takes parameters from the **Add Mail** dialog box that is displayed when you click the **Add Mail** command on the **Addins** menu in the MFCMAPI sample application.</span></span> <span data-ttu-id="1e4ad-117">在`DisplayAddMailDialog`邮件中, cpp 中的函数显示对话框, 并将对话框中的值传递给`AddMail`函数。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-117">The  `DisplayAddMailDialog` function in Mails.cpp displays the dialog box and passes the values from the dialog box to the  `AddMail` function.</span></span> <span data-ttu-id="1e4ad-118">该`DisplayAddMailDialog`函数与使用 MAPI 创建邮件项目不直接相关, 因此此处未列出它。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-118">The  `DisplayAddMailDialog` function does not relate directly to creating a mail item using MAPI, so it is not listed here.</span></span> <span data-ttu-id="1e4ad-119">`AddMail`函数如下所示。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-119">The  `AddMail` function is listed below.</span></span> 
  
<span data-ttu-id="1e4ad-120">请注意, __ 传递给该`AddMail`方法的 lpFolder 参数是一个指向[IMAPIFolder](imapifolderimapicontainer.md)接口的指针, 该接口表示将在其中创建新邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-120">Note that the  _lpFolder_ parameter passed to the  `AddMail` method is a pointer to an [IMAPIFolder](imapifolderimapicontainer.md) interface that represents the folder where the new message will be created.</span></span> <span data-ttu-id="1e4ad-121">给定表示**IMAPIFolder**接口的_lpFolder_参数, 该代码调用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-121">Given the  _lpFolder_ parameter that represents an **IMAPIFolder** interface, the code calls the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="1e4ad-122">**CreateMessage**方法返回一个成功代码和一个指向[IMessage: IMAPIProp](imessageimapiprop.md)接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-122">The **CreateMessage** method returns a success code and a pointer to a pointer to an [IMessage : IMAPIProp](imessageimapiprop.md) interface.</span></span> 

<span data-ttu-id="1e4ad-123">大部分`AddMail`函数代码处理设置属性的工作, 以便为调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法做准备。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-123">Most of the  `AddMail` function code handles the work of setting properties in preparation for calling the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="1e4ad-124">如果对**SetProps**方法的调用成功, 则对[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的调用将更改提交到存储, 并创建一个新的邮件项目。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-124">If the call to the **SetProps** method succeeds, a call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method commits the changes to the store and creates a new mail item.</span></span> <span data-ttu-id="1e4ad-125">然后, 如果请求, 则调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法发送邮件。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-125">Then, if requested, the [IMessage::SubmitMessage](imessage-submitmessage.md) method is called to send the message.</span></span> 
  
<span data-ttu-id="1e4ad-126">`AddMail`函数使用两个 helper 函数来生成**PR_CONVERSATION_INDEX**和**PR_REPORT_TAG**属性的值: `BuildConversationIndex`和`AddReportTag`函数。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-126">The  `AddMail` function uses two helper functions to build values for the **PR_CONVERSATION_INDEX** and **PR_REPORT_TAG** properties: the  `BuildConversationIndex` and  `AddReportTag` functions.</span></span> <span data-ttu-id="1e4ad-127">`BuildConversationIndex`函数 (位于 CreateOutlookItemsAddin 中) 执行内置 MAPI [ScCreateConversationIndex](sccreateconversationindex.md)函数在不向其传递父会话索引时所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-127">The  `BuildConversationIndex` function, located in CreateOutlookItemsAddin.cpp, does the same work that the built-in MAPI [ScCreateConversationIndex](sccreateconversationindex.md) function does when a parent conversation index is not passed to it.</span></span> <span data-ttu-id="1e4ad-128">在[PidTagConversationIndex 规范属性](pidtagconversationindex-canonical-property.md)中记录了这些函数生成的会话索引缓冲区的格式。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-128">The format of the conversation index buffer that these functions generate is documented in [PidTagConversationIndex Canonical Property](pidtagconversationindex-canonical-property.md).</span></span> 

<span data-ttu-id="1e4ad-129">位于`AddReportTag` "PR_REPORT_TAG" 中的函数又调用`BuildReportTag`函数来生成\*\*\*\* 属性的结构。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-129">The  `AddReportTag` function, located in Mails.cpp, in turn calls the  `BuildReportTag` function to build a structure for the **PR_REPORT_TAG** property.</span></span> <span data-ttu-id="1e4ad-130">有关`BuildReportTag`函数生成的结构的信息, 请参阅[PidTagReportTag 规范属性](pidtagreporttag-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-130">For information about the structure that the  `BuildReportTag` function builds, see [PidTagReportTag Canonical Property](pidtagreporttag-canonical-property.md).</span></span>
  
<span data-ttu-id="1e4ad-131">下面是该`AddMail`函数的完整列表。</span><span class="sxs-lookup"><span data-stu-id="1e4ad-131">The following is the complete listing of the  `AddMail` function.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="1e4ad-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e4ad-132">See also</span></span>

- [<span data-ttu-id="1e4ad-133">使用 MAPI 创建 Outlook 2007 项目</span><span class="sxs-lookup"><span data-stu-id="1e4ad-133">Using MAPI to Create Outlook 2007 Items</span></span>](https://msdn.microsoft.com/library/cc678348%28office.12%29.aspx)

