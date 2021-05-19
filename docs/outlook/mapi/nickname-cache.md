---
title: 别名缓存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2813c102-6778-4443-ab4b-b573f3568705
description: 上次修改时间：2013 年 1 月 30 日
ms.openlocfilehash: 841b01ae8dfcf841b0a1d64113ce7258c4c61583
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334515"
---
# <a name="nickname-cache"></a><span data-ttu-id="62dfa-103">别名缓存</span><span class="sxs-lookup"><span data-stu-id="62dfa-103">Nickname cache</span></span>

 
  
<span data-ttu-id="62dfa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="62dfa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="62dfa-105">Microsoft Office Outlook 2007、Microsoft Outlook 2010 和 Microsoft Outlook 2013 与昵称缓存交互，也称为"自动完成流"。</span><span class="sxs-lookup"><span data-stu-id="62dfa-105">Microsoft Office Outlook 2007, Microsoft Outlook 2010, and Microsoft Outlook 2013 interact with the nickname cache, also known as the "autocomplete stream."</span></span> <span data-ttu-id="62dfa-106">自动完成流是 Outlook保留自动完成列表的位置，该列表是用户在撰写电子邮件时显示在"To"、Cc 和 **"Bcc"** 编辑框中的名称列表。</span><span class="sxs-lookup"><span data-stu-id="62dfa-106">The autocomplete stream is where Outlook persists the autocomplete list, which is the list of names that displays in the **To**, **Cc**, and **Bcc** edit boxes while a user is composing an email.</span></span> <span data-ttu-id="62dfa-107">本主题介绍 Outlook 2007、Outlook 2010 和 Outlook 2013 如何与自动完成流交互，并讨论文件的二进制格式以及与自动完成流交互的建议方法。</span><span class="sxs-lookup"><span data-stu-id="62dfa-107">This topic describes how Outlook 2007, Outlook 2010, and Outlook 2013 interact with the autocomplete stream and also discusses the binary format of the file and the recommended ways for interacting with the autocomplete stream.</span></span> 
  
<span data-ttu-id="62dfa-108">对于与 Outlook 2010 或 Outlook 2013 交互的应用程序，自动完成流存储为 MAPI 属性，并且可以使用邮件的 MAPI 或 **PropertyAccessor** 对象进行修改。</span><span class="sxs-lookup"><span data-stu-id="62dfa-108">For applications that interact with Outlook 2010 or Outlook 2013, the autocomplete stream is stored as a MAPI property and can be modified using the MAPI or the **PropertyAccessor** object of the message.</span></span> <span data-ttu-id="62dfa-109">**PropertyAccessor** 对象在 Outlook 2010 或 Outlook 2013 对象模型中公开。</span><span class="sxs-lookup"><span data-stu-id="62dfa-109">The **PropertyAccessor** object is exposed in the Outlook 2010 or Outlook 2013 object models.</span></span> 
  
<span data-ttu-id="62dfa-110">2007 对象模型Outlook MAPI API 没有依赖关系。</span><span class="sxs-lookup"><span data-stu-id="62dfa-110">There are no dependencies on the Outlook 2007 object model or MAPI APIs.</span></span> <span data-ttu-id="62dfa-111">因此，在 2007 Outlook自动完成流的应用程序可以使用任何编程语言编写。</span><span class="sxs-lookup"><span data-stu-id="62dfa-111">Therefore, applications that make changes to the autocomplete stream within Outlook 2007 can be written using any programming language.</span></span>
  
## <a name="interacting-with-the-autocomplete-stream"></a><span data-ttu-id="62dfa-112">与自动完成流交互</span><span class="sxs-lookup"><span data-stu-id="62dfa-112">Interacting with the Autocomplete Stream</span></span>

<span data-ttu-id="62dfa-113">在邮件 **上** 访问"收件人"、"抄送"或"**密** 件抄送"编辑框时，将加载自动完成流并显示用户名列表。</span><span class="sxs-lookup"><span data-stu-id="62dfa-113">When the **To**, **Cc**, or **Bcc** edit boxes are accessed on a message, the autocomplete stream is loaded and the list of user names is displayed.</span></span> <span data-ttu-id="62dfa-114">Outlook两种方式与自动完成流交互：</span><span class="sxs-lookup"><span data-stu-id="62dfa-114">Outlook interacts with the autocomplete stream in two ways:</span></span> 
  
1. <span data-ttu-id="62dfa-115">加载自动完成流</span><span class="sxs-lookup"><span data-stu-id="62dfa-115">Loading the autocomplete stream</span></span> 
    
2. <span data-ttu-id="62dfa-116">保存对自动完成流中数据的更改</span><span class="sxs-lookup"><span data-stu-id="62dfa-116">Saving changes to the data in the autocomplete stream</span></span>
    
<span data-ttu-id="62dfa-117">存储自动完成数据的方式在 Outlook 2007 和 Outlook 2010 或 Outlook 2013 之间有所不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="62dfa-117">The means of storing the autocomplete data differs between Outlook 2007 and Outlook 2010 or Outlook 2013 as follows:</span></span> 
  
 <span data-ttu-id="62dfa-118">**Outlook 2007**</span><span class="sxs-lookup"><span data-stu-id="62dfa-118">**Outlook 2007**</span></span>
  
<span data-ttu-id="62dfa-119">对于 Outlook 2007，自动完成流存储在与配置文件同名且扩展名为 .nk2 的文件中。</span><span class="sxs-lookup"><span data-stu-id="62dfa-119">For Outlook 2007, the autocomplete stream is stored in a file with the same name as the profile and an extension of .nk2.</span></span> <span data-ttu-id="62dfa-120">例如，如果使用默认配置文件"outlook"，则该文件将被称为"outlook.nk2"。</span><span class="sxs-lookup"><span data-stu-id="62dfa-120">For example, if the default profile of "outlook" is used, the file will be called "outlook.nk2".</span></span> <span data-ttu-id="62dfa-121">.nk2 文件存储在 %APPDATA%\Microsoft\Outlook。</span><span class="sxs-lookup"><span data-stu-id="62dfa-121">The .nk2 file is stored in %APPDATA%\Microsoft\Outlook.</span></span> <span data-ttu-id="62dfa-122">有关昵称缓存二进制文件格式的信息，请参阅 Outlook [2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。</span><span class="sxs-lookup"><span data-stu-id="62dfa-122">For more information about the nickname cache binary file format, see [Outlook 2003/2007 NK2 File Format and Developer Guidelines](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf).</span></span>
  
 <span data-ttu-id="62dfa-123">**Outlook 2010 和 Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="62dfa-123">**Outlook 2010 and Outlook 2013**</span></span>
  
<span data-ttu-id="62dfa-124">Outlook 2010 或 Outlook 2013 从邮件帐户传递存储的"收件箱"的"关联内容"表中的邮件读取自动完成流。</span><span class="sxs-lookup"><span data-stu-id="62dfa-124">Outlook 2010 or Outlook 2013 reads the autocomplete stream from a message in the Associated Contents table of the Inbox of the mail account's delivery store.</span></span> <span data-ttu-id="62dfa-125">此隐藏邮件包含邮件类别和IPM.Config消息。自动完成。</span><span class="sxs-lookup"><span data-stu-id="62dfa-125">This hidden message has a message class and subject of IPM.Configuration.Autocomplete.</span></span> <span data-ttu-id="62dfa-126">自动完成流存储在此消息的 PR_ROAMING_BINARYSTREAM 属性 ([PidTagRoamingBinary](pidtagroamingbinary-canonical-property.md) 规范属性) 。</span><span class="sxs-lookup"><span data-stu-id="62dfa-126">The autocomplete stream is stored on this message in the PR_ROAMING_BINARYSTREAM property ([PidTagRoamingBinary Canonical Property](pidtagroamingbinary-canonical-property.md)).</span></span> <span data-ttu-id="62dfa-127">自动完成数据可能临时缓存在位于 %USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache 中的自动完成 .dat 文件中。</span><span class="sxs-lookup"><span data-stu-id="62dfa-127">The autocomplete data may be temporarily cached in an autocomplete .dat file located in %USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache.</span></span> <span data-ttu-id="62dfa-128">但是，.d Outlook at 文件只是一个缓存，在用户退出 2010 或 Outlook 2013 时，不会用于写回传递存储区。</span><span class="sxs-lookup"><span data-stu-id="62dfa-128">However, the .dat file is only a cache and is not used to write back to the delivery store when the user exits Outlook 2010 or Outlook 2013.</span></span>
  
## <a name="loading-the-autocomplete-stream"></a><span data-ttu-id="62dfa-129">加载自动完成流</span><span class="sxs-lookup"><span data-stu-id="62dfa-129">Loading the Autocomplete Stream</span></span>

<span data-ttu-id="62dfa-130">Outlook具有寻址功能的项时加载自动完成流。</span><span class="sxs-lookup"><span data-stu-id="62dfa-130">Outlook loads the autocomplete stream whenever an item with addressing functionality is initialized.</span></span> <span data-ttu-id="62dfa-131">例如，电子邮件地址用于新邮件、邮件答复、联系人项目、会议请求等。</span><span class="sxs-lookup"><span data-stu-id="62dfa-131">For example, email addresses are used in a new mail, a mail reply, a contact item, a meeting request, and so on.</span></span> <span data-ttu-id="62dfa-132">若要加载数据，Outlook将流中所有的内容读取到内存中。</span><span class="sxs-lookup"><span data-stu-id="62dfa-132">To load the data, Outlook reads all of the contents of the stream into memory.</span></span>
  
<span data-ttu-id="62dfa-133">对于自动完成操作，Outlook在进程生存期内以独占方式与此内存outlook.exe交互。</span><span class="sxs-lookup"><span data-stu-id="62dfa-133">For autocomplete operations, Outlook interacts exclusively with this in-memory structure for the duration of the outlook.exe process lifetime.</span></span> <span data-ttu-id="62dfa-134">Outlook关闭时仅保存结构。</span><span class="sxs-lookup"><span data-stu-id="62dfa-134">Outlook only saves the structure on shutdown.</span></span> <span data-ttu-id="62dfa-135">有关此过程详细信息，请参阅以下"保存自动完成流"部分。</span><span class="sxs-lookup"><span data-stu-id="62dfa-135">See the following section "Saving the Autocomplete Stream" for more information on this process.</span></span>
  
## <a name="saving-the-autocomplete-stream"></a><span data-ttu-id="62dfa-136">保存自动完成流</span><span class="sxs-lookup"><span data-stu-id="62dfa-136">Saving the Autocomplete Stream</span></span>

<span data-ttu-id="62dfa-137">Outlook以下列任一方式更改自动完成列表时，自动完成流在关闭时保存：</span><span class="sxs-lookup"><span data-stu-id="62dfa-137">Outlook saves the autocomplete stream on shutdown if the autocomplete list has changed in any of the following ways:</span></span>
  
- <span data-ttu-id="62dfa-138">通过解析姓名、从通讯簿对话框中选取收件人或向列表中尚未包含的收件人发送邮件来添加新的昵称条目。</span><span class="sxs-lookup"><span data-stu-id="62dfa-138">A new nickname entry is added through resolving a name, picking a recipient from the address book dialog, or sending mail to a recipient that was not already in the list.</span></span>
    
- <span data-ttu-id="62dfa-139">通过向列表中的现有收件人发送邮件来修改条目。</span><span class="sxs-lookup"><span data-stu-id="62dfa-139">An entry is modified by sending mail to an existing recipient in the list.</span></span>
    
- <span data-ttu-id="62dfa-140">用户通过 UI 删除条目。</span><span class="sxs-lookup"><span data-stu-id="62dfa-140">An entry is removed by the user through the UI.</span></span>
    
- <span data-ttu-id="62dfa-141">与本主题不相关的其他次要方案。</span><span class="sxs-lookup"><span data-stu-id="62dfa-141">Other minor scenarios not relevant to this topic.</span></span>
    
<span data-ttu-id="62dfa-142">保存对自动完成数据所做的更改涉及将内存中的结构写回 [自动完成 Stream](autocomplete-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="62dfa-142">Saving changes to the autocomplete data involves writing the in-memory structure back to an [Autocomplete Stream](autocomplete-stream.md).</span></span> <span data-ttu-id="62dfa-143">与 Outlook 2007 交互时，流将保存到本地 .nk2 文件中。</span><span class="sxs-lookup"><span data-stu-id="62dfa-143">When interacting with Outlook 2007, the stream is saved to a local .nk2 file.</span></span> <span data-ttu-id="62dfa-144">对于 Outlook 2010 或 Outlook 2013，自动完成流写回邮件帐户传递存储的"收件箱"的"关联内容"表。</span><span class="sxs-lookup"><span data-stu-id="62dfa-144">For Outlook 2010 or Outlook 2013, the autocomplete stream writes back to the Associated Contents table of the Inbox of the mail account's delivery store.</span></span>
  
## <a name="recommendations"></a><span data-ttu-id="62dfa-145">建议</span><span class="sxs-lookup"><span data-stu-id="62dfa-145">Recommendations</span></span>

- <span data-ttu-id="62dfa-146">从不部分修改自动完成流。</span><span class="sxs-lookup"><span data-stu-id="62dfa-146">Never partially modify the autocomplete stream.</span></span> <span data-ttu-id="62dfa-147">支持的交互为 1，) 将整个自动完成流读取到内存中， 2) 修改内存结构，3) 将整个流写回 (for Outlook 2010 或 Outlook 2013) 的收件箱的"关联内容"表或本地 .nk2 文件 (Outlook 2007) 。</span><span class="sxs-lookup"><span data-stu-id="62dfa-147">The supported interaction is to 1) read the entire autocomplete stream into memory, 2) modify the memory structure, and 3) write the entire stream back to either the Associated Contents table of the Inbox of the mail account's delivery store (for Outlook 2010 or Outlook 2013) or to the local .nk2 file (Outlook 2007).</span></span>
    
- <span data-ttu-id="62dfa-148">在运行自动完成流时，不要Outlook自动完成流。</span><span class="sxs-lookup"><span data-stu-id="62dfa-148">Do not interact with the autocomplete stream while Outlook is running.</span></span> <span data-ttu-id="62dfa-149">如果在Outlook流时运行，则它可能会在关闭时覆盖所做的更改。</span><span class="sxs-lookup"><span data-stu-id="62dfa-149">If Outlook is running while you modify the stream, it will likely overwrite your changes when it shuts down.</span></span>
    
- <span data-ttu-id="62dfa-150">不要将类型为 PT_MV_UNICODE 的属性PR_MV_STRING8写入 Microsoft Outlook 2003 使用的自动完成流中。</span><span class="sxs-lookup"><span data-stu-id="62dfa-150">Do not write properties of type PT_MV_UNICODE and PR_MV_STRING8 into an autocomplete stream to be consumed by Microsoft Outlook 2003.</span></span> <span data-ttu-id="62dfa-151">这些属性仅在 2007 Outlook 2010 Outlook 2013 Outlook理解。</span><span class="sxs-lookup"><span data-stu-id="62dfa-151">These properties are only understood by Outlook 2007, Outlook 2010, and Outlook 2013.</span></span>
    
- <span data-ttu-id="62dfa-152">开发与 Outlook 2007 交互的代码时，我们建议您在使用标准文件锁定 API（例如，C/C++ 中的 **LockFile** 和 C#) 中的 **FileStream.Lock）** 读取和写入文件时锁定 .nk (2 文件，以便其他进程修改该文件。</span><span class="sxs-lookup"><span data-stu-id="62dfa-152">When developing code that interacts with Outlook 2007, we recommend that you lock the .nk2 file from modification by other processes while you are reading and writing it using standard file locking APIs (for example, **LockFile** in C/C++ and **FileStream.Lock** in C#).</span></span> 
    
- <span data-ttu-id="62dfa-153">仅修改来自自动完成流的行集的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="62dfa-153">Only modify the properties of types that are from the row-set of the autocomplete stream.</span></span> <span data-ttu-id="62dfa-154">有关自动完成流属性和属性类型的信息，请参阅 [自动完成流](autocomplete-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="62dfa-154">For more information about the autocomplete stream properties and property types, see [Autocomplete Stream](autocomplete-stream.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="62dfa-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62dfa-155">See also</span></span>



[<span data-ttu-id="62dfa-156">自动完成 Stream</span><span class="sxs-lookup"><span data-stu-id="62dfa-156">Autocomplete Stream</span></span>](autocomplete-stream.md)
  
[<span data-ttu-id="62dfa-157">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="62dfa-157">MAPI Profiles</span></span>](mapi-profiles.md)


[<span data-ttu-id="62dfa-158">Outlook 2003/2007 NK2 文件格式和开发人员指南</span><span class="sxs-lookup"><span data-stu-id="62dfa-158">Outlook 2003/2007 NK2 File Format and Developer Guidelines</span></span>](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)

