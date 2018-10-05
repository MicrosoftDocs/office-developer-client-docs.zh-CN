---
title: 别名缓存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2813c102-6778-4443-ab4b-b573f3568705
description: 上次修改时间： 2013 年 1 月 30 日
ms.openlocfilehash: 841b01ae8dfcf841b0a1d64113ce7258c4c61583
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389258"
---
# <a name="nickname-cache"></a><span data-ttu-id="42ed2-103">别名缓存</span><span class="sxs-lookup"><span data-stu-id="42ed2-103">Nickname cache</span></span>

 
  
<span data-ttu-id="42ed2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="42ed2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="42ed2-105">Microsoft Office Outlook 2007、 Microsoft Outlook 2010 和 Microsoft Outlook 2013 交互昵称缓存，也称为"记忆式键入流。"</span><span class="sxs-lookup"><span data-stu-id="42ed2-105">Microsoft Office Outlook 2007, Microsoft Outlook 2010, and Microsoft Outlook 2013 interact with the nickname cache, also known as the "autocomplete stream."</span></span> <span data-ttu-id="42ed2-106">记忆式键入流是 Outlook 仍然存在记忆式键入列表，这是在**到**、**抄送**，显示名称的列表和**密件抄送**编辑框时用户撰写电子邮件时的位置。</span><span class="sxs-lookup"><span data-stu-id="42ed2-106">The autocomplete stream is where Outlook persists the autocomplete list, which is the list of names that displays in the **To**, **Cc**, and **Bcc** edit boxes while a user is composing an email.</span></span> <span data-ttu-id="42ed2-107">本主题介绍 Outlook 2007、 Outlook 2010 和 Outlook 2013 如何记忆式键入流交互，并讨论该文件，用于与记忆式键入流进行交互的建议的方式的二进制格式。</span><span class="sxs-lookup"><span data-stu-id="42ed2-107">This topic describes how Outlook 2007, Outlook 2010, and Outlook 2013 interact with the autocomplete stream and also discusses the binary format of the file and the recommended ways for interacting with the autocomplete stream.</span></span> 
  
<span data-ttu-id="42ed2-108">对于 Outlook 2010 或 Outlook 2013 与之交互的应用程序，记忆式键入流存储为 MAPI 属性，可以使用 MAPI 或邮件的**PropertyAccessor**对象进行修改。</span><span class="sxs-lookup"><span data-stu-id="42ed2-108">For applications that interact with Outlook 2010 or Outlook 2013, the autocomplete stream is stored as a MAPI property and can be modified using the MAPI or the **PropertyAccessor** object of the message.</span></span> <span data-ttu-id="42ed2-109">Outlook 2010 或 Outlook 2013 对象模型中公开**PropertyAccessor**对象。</span><span class="sxs-lookup"><span data-stu-id="42ed2-109">The **PropertyAccessor** object is exposed in the Outlook 2010 or Outlook 2013 object models.</span></span> 
  
<span data-ttu-id="42ed2-110">没有依赖 Outlook 2007 对象模型或 MAPI Api。</span><span class="sxs-lookup"><span data-stu-id="42ed2-110">There are no dependencies on the Outlook 2007 object model or MAPI APIs.</span></span> <span data-ttu-id="42ed2-111">因此，可以使用任何编程语言编写的应用程序对 Outlook 2007 中的记忆式键入流进行更改。</span><span class="sxs-lookup"><span data-stu-id="42ed2-111">Therefore, applications that make changes to the autocomplete stream within Outlook 2007 can be written using any programming language.</span></span>
  
## <a name="interacting-with-the-autocomplete-stream"></a><span data-ttu-id="42ed2-112">与记忆式键入流交互</span><span class="sxs-lookup"><span data-stu-id="42ed2-112">Interacting with the Autocomplete Stream</span></span>

<span data-ttu-id="42ed2-113">**到**、**抄送**或**密件抄送**编辑框访问上一条消息时, 记忆式键入流加载和显示用户的用户名的列表。</span><span class="sxs-lookup"><span data-stu-id="42ed2-113">When the **To**, **Cc**, or **Bcc** edit boxes are accessed on a message, the autocomplete stream is loaded and the list of user names is displayed.</span></span> <span data-ttu-id="42ed2-114">Outlook 与以下两种方式记忆式键入流进行交互：</span><span class="sxs-lookup"><span data-stu-id="42ed2-114">Outlook interacts with the autocomplete stream in two ways:</span></span> 
  
1. <span data-ttu-id="42ed2-115">加载记忆式键入流</span><span class="sxs-lookup"><span data-stu-id="42ed2-115">Loading the autocomplete stream</span></span> 
    
2. <span data-ttu-id="42ed2-116">将更改保存到记忆式键入流中的数据</span><span class="sxs-lookup"><span data-stu-id="42ed2-116">Saving changes to the data in the autocomplete stream</span></span>
    
<span data-ttu-id="42ed2-117">存储记忆式键入数据的方式与 Outlook 2007 和 Outlook 2010 或 Outlook 2013 之间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="42ed2-117">The means of storing the autocomplete data differs between Outlook 2007 and Outlook 2010 or Outlook 2013 as follows:</span></span> 
  
 <span data-ttu-id="42ed2-118">**Outlook 2007**</span><span class="sxs-lookup"><span data-stu-id="42ed2-118">**Outlook 2007**</span></span>
  
<span data-ttu-id="42ed2-119">为 Outlook 2007 记忆式键入流存储在具有相同名称配置文件和.nk2 扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="42ed2-119">For Outlook 2007, the autocomplete stream is stored in a file with the same name as the profile and an extension of .nk2.</span></span> <span data-ttu-id="42ed2-120">例如，如果使用的"outlook"的默认配置文件，则该文件将调用"outlook.nk2"。</span><span class="sxs-lookup"><span data-stu-id="42ed2-120">For example, if the default profile of "outlook" is used, the file will be called "outlook.nk2".</span></span> <span data-ttu-id="42ed2-121">.Nk2 文件存储在 %appdata%\microsoft\outlook。</span><span class="sxs-lookup"><span data-stu-id="42ed2-121">The .nk2 file is stored in %APPDATA%\Microsoft\Outlook.</span></span> <span data-ttu-id="42ed2-122">有关昵称缓存二进制文件格式的详细信息，请参阅[Outlook 2003/2007 NK2 文件格式和开发人员的准则](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。</span><span class="sxs-lookup"><span data-stu-id="42ed2-122">For more information about the nickname cache binary file format, see [Outlook 2003/2007 NK2 File Format and Developer Guidelines](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf).</span></span>
  
 <span data-ttu-id="42ed2-123">**Outlook 2010 和 Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="42ed2-123">**Outlook 2010 and Outlook 2013**</span></span>
  
<span data-ttu-id="42ed2-124">Outlook 2010 或 Outlook 2013 中从关联的内容表中的邮件帐户的传递存储区的收件箱中的邮件读取记忆式键入流。</span><span class="sxs-lookup"><span data-stu-id="42ed2-124">Outlook 2010 or Outlook 2013 reads the autocomplete stream from a message in the Associated Contents table of the Inbox of the mail account's delivery store.</span></span> <span data-ttu-id="42ed2-125">此隐藏的邮件具有邮件类和 IPM 的主题。Configuration.Autocomplete。</span><span class="sxs-lookup"><span data-stu-id="42ed2-125">This hidden message has a message class and subject of IPM.Configuration.Autocomplete.</span></span> <span data-ttu-id="42ed2-126">记忆式键入流 PR_ROAMING_BINARYSTREAM 属性 （[PidTagRoamingBinary 规范属性](pidtagroamingbinary-canonical-property.md)） 中的此邮件上存储。</span><span class="sxs-lookup"><span data-stu-id="42ed2-126">The autocomplete stream is stored on this message in the PR_ROAMING_BINARYSTREAM property ([PidTagRoamingBinary Canonical Property](pidtagroamingbinary-canonical-property.md)).</span></span> <span data-ttu-id="42ed2-127">Autocomplete 数据可能会临时缓存位于 %userprofile%\appdata\local\microsoft\outlook\roamcache 记忆式键入.dat 文件中。</span><span class="sxs-lookup"><span data-stu-id="42ed2-127">The autocomplete data may be temporarily cached in an autocomplete .dat file located in %USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache.</span></span> <span data-ttu-id="42ed2-128">但是，.dat 文件是仅缓存，并且不用于在用户退出 Outlook 2010 或 Outlook 2013 时，回写到传递存储区。</span><span class="sxs-lookup"><span data-stu-id="42ed2-128">However, the .dat file is only a cache and is not used to write back to the delivery store when the user exits Outlook 2010 or Outlook 2013.</span></span>
  
## <a name="loading-the-autocomplete-stream"></a><span data-ttu-id="42ed2-129">加载记忆式键入流</span><span class="sxs-lookup"><span data-stu-id="42ed2-129">Loading the Autocomplete Stream</span></span>

<span data-ttu-id="42ed2-130">Outlook 加载记忆式键入流，当初始化具有寻址的功能的项。</span><span class="sxs-lookup"><span data-stu-id="42ed2-130">Outlook loads the autocomplete stream whenever an item with addressing functionality is initialized.</span></span> <span data-ttu-id="42ed2-131">例如，新邮件、 邮件答复、 联系人项目、 会议请求中，依次类推中使用电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="42ed2-131">For example, email addresses are used in a new mail, a mail reply, a contact item, a meeting request, and so on.</span></span> <span data-ttu-id="42ed2-132">若要加载的数据，Outlook 将 stream 的内容的所有读入内存。</span><span class="sxs-lookup"><span data-stu-id="42ed2-132">To load the data, Outlook reads all of the contents of the stream into memory.</span></span>
  
<span data-ttu-id="42ed2-133">记忆式键入操作的 Outlook 进行交互以独占方式使用该内存中结构 outlook.exe 进程的生存期内的持续时间内。</span><span class="sxs-lookup"><span data-stu-id="42ed2-133">For autocomplete operations, Outlook interacts exclusively with this in-memory structure for the duration of the outlook.exe process lifetime.</span></span> <span data-ttu-id="42ed2-134">Outlook 仅保存在关闭的结构。</span><span class="sxs-lookup"><span data-stu-id="42ed2-134">Outlook only saves the structure on shutdown.</span></span> <span data-ttu-id="42ed2-135">在此过程，请参阅下一节"保存记忆式键入流"的详细信息。</span><span class="sxs-lookup"><span data-stu-id="42ed2-135">See the following section "Saving the Autocomplete Stream" for more information on this process.</span></span>
  
## <a name="saving-the-autocomplete-stream"></a><span data-ttu-id="42ed2-136">保存记忆式键入流</span><span class="sxs-lookup"><span data-stu-id="42ed2-136">Saving the Autocomplete Stream</span></span>

<span data-ttu-id="42ed2-137">如果记忆式键入列表中任何通过以下方式已更改，则 outlook 将在关闭保存记忆式键入流：</span><span class="sxs-lookup"><span data-stu-id="42ed2-137">Outlook saves the autocomplete stream on shutdown if the autocomplete list has changed in any of the following ways:</span></span>
  
- <span data-ttu-id="42ed2-138">通过解析名称、 选取通讯簿对话框中，从收件人或将邮件发送给收件人列表中已不存在添加一个新的昵称条目。</span><span class="sxs-lookup"><span data-stu-id="42ed2-138">A new nickname entry is added through resolving a name, picking a recipient from the address book dialog, or sending mail to a recipient that was not already in the list.</span></span>
    
- <span data-ttu-id="42ed2-139">通过将邮件发送到现有收件人列表中，将修改条目。</span><span class="sxs-lookup"><span data-stu-id="42ed2-139">An entry is modified by sending mail to an existing recipient in the list.</span></span>
    
- <span data-ttu-id="42ed2-140">由用户通过用户界面删除了一个条目。</span><span class="sxs-lookup"><span data-stu-id="42ed2-140">An entry is removed by the user through the UI.</span></span>
    
- <span data-ttu-id="42ed2-141">其他与本主题不相关的次要方案。</span><span class="sxs-lookup"><span data-stu-id="42ed2-141">Other minor scenarios not relevant to this topic.</span></span>
    
<span data-ttu-id="42ed2-142">将更改保存到记忆式键入数据涉及到[记忆式键入流](autocomplete-stream.md)重新编写内存中的结构。</span><span class="sxs-lookup"><span data-stu-id="42ed2-142">Saving changes to the autocomplete data involves writing the in-memory structure back to an [Autocomplete Stream](autocomplete-stream.md).</span></span> <span data-ttu-id="42ed2-143">当与 Outlook 2007 中交互，流被保存到本地.nk2 文件。</span><span class="sxs-lookup"><span data-stu-id="42ed2-143">When interacting with Outlook 2007, the stream is saved to a local .nk2 file.</span></span> <span data-ttu-id="42ed2-144">对于 Outlook 2010 或 Outlook 2013，记忆式键入流将写回关联的内容表中的邮件帐户的传递存储区的收件箱。</span><span class="sxs-lookup"><span data-stu-id="42ed2-144">For Outlook 2010 or Outlook 2013, the autocomplete stream writes back to the Associated Contents table of the Inbox of the mail account's delivery store.</span></span>
  
## <a name="recommendations"></a><span data-ttu-id="42ed2-145">建议</span><span class="sxs-lookup"><span data-stu-id="42ed2-145">Recommendations</span></span>

- <span data-ttu-id="42ed2-146">从不部分修改记忆式键入流。</span><span class="sxs-lookup"><span data-stu-id="42ed2-146">Never partially modify the autocomplete stream.</span></span> <span data-ttu-id="42ed2-147">支持的交互是 1） 的整个记忆式键入流读取到内存和 2） 修改的内存结构，3） 整个流回写到以下任意关联的内容表中的邮件帐户的传递存储区的收件箱 (Outlook 2010 或Outlook 2013) 或本地.nk2 文件 (Outlook 2007)。</span><span class="sxs-lookup"><span data-stu-id="42ed2-147">The supported interaction is to 1) read the entire autocomplete stream into memory, 2) modify the memory structure, and 3) write the entire stream back to either the Associated Contents table of the Inbox of the mail account's delivery store (for Outlook 2010 or Outlook 2013) or to the local .nk2 file (Outlook 2007).</span></span>
    
- <span data-ttu-id="42ed2-148">不进行交互与记忆式键入数据流运行 Outlook 时。</span><span class="sxs-lookup"><span data-stu-id="42ed2-148">Do not interact with the autocomplete stream while Outlook is running.</span></span> <span data-ttu-id="42ed2-149">如果 Outlook 正在运行时修改流，它将其关闭时，可能覆盖所做的更改。</span><span class="sxs-lookup"><span data-stu-id="42ed2-149">If Outlook is running while you modify the stream, it will likely overwrite your changes when it shuts down.</span></span>
    
- <span data-ttu-id="42ed2-150">执行操作的不写入属性键入 PT_MV_UNICODE 和 PR_MV_STRING8 到要由 Microsoft Outlook 2003 记忆式键入流。</span><span class="sxs-lookup"><span data-stu-id="42ed2-150">Do not write properties of type PT_MV_UNICODE and PR_MV_STRING8 into an autocomplete stream to be consumed by Microsoft Outlook 2003.</span></span> <span data-ttu-id="42ed2-151">Outlook 2007、 Outlook 2010 和 Outlook 2013 仅理解这些属性。</span><span class="sxs-lookup"><span data-stu-id="42ed2-151">These properties are only understood by Outlook 2007, Outlook 2010, and Outlook 2013.</span></span>
    
- <span data-ttu-id="42ed2-152">开发与 Outlook 2007 交互的代码时，我们建议您锁定其他进程中修改的.nk2 文件时要读取和写入它使用标准文件锁定 Api (例如，**锁定文件**C/c + + 和**中FileStream.Lock**中 C#)。</span><span class="sxs-lookup"><span data-stu-id="42ed2-152">When developing code that interacts with Outlook 2007, we recommend that you lock the .nk2 file from modification by other processes while you are reading and writing it using standard file locking APIs (for example, **LockFile** in C/C++ and **FileStream.Lock** in C#).</span></span> 
    
- <span data-ttu-id="42ed2-153">只能修改从记忆式键入流行集中的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="42ed2-153">Only modify the properties of types that are from the row-set of the autocomplete stream.</span></span> <span data-ttu-id="42ed2-154">有关记忆式键入流属性和属性类型的详细信息，请参阅[记忆式键入流](autocomplete-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="42ed2-154">For more information about the autocomplete stream properties and property types, see [Autocomplete Stream](autocomplete-stream.md).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="42ed2-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42ed2-155">See also</span></span>



[<span data-ttu-id="42ed2-156">自动完成流</span><span class="sxs-lookup"><span data-stu-id="42ed2-156">Autocomplete Stream</span></span>](autocomplete-stream.md)
  
[<span data-ttu-id="42ed2-157">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="42ed2-157">MAPI Profiles</span></span>](mapi-profiles.md)


[<span data-ttu-id="42ed2-158">Outlook 2003/2007 NK2 文件格式和开发人员指南</span><span class="sxs-lookup"><span data-stu-id="42ed2-158">Outlook 2003/2007 NK2 File Format and Developer Guidelines</span></span>](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)

