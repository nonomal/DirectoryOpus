# 音乐属性

**音乐属性**元数据字段适用于音乐文件——Opus 当前支持的格式为**MP3** 和**WMA**。多个**音乐**字段也适用于 [视频](video_properties.zh.md) 文件。

- **专辑**: 此音乐所在的专辑标题。
- **专辑艺术家**: 专辑艺术家。字段的具体用法由您决定——通常用于每首曲目艺术家可能不同的合辑专辑。
- **艺术家**: 此曲目负责的艺术家或多位艺术家。此字段与**作者 [文档属性](document_properties.zh.md)** 字段相同（已重命名）。若要指定多个艺术家，请用分号分隔（在多个不同的元数据字段中都采用此方法提供多个值）。
- **作者 URL**: 与艺术家关联的 URL（例如，乐队网站的 URL）。
- **BPM**: 音乐的速度，以每分钟节拍数表示。
- **作曲者**: 音乐的作曲者或多位作曲者。若要指定多个作曲者，请用分号分隔。
- **指挥家**: 音乐的指挥家或多位指挥家。若要指定多个指挥家，请用分号分隔。
- **内容组**: 此字段让您将不同的曲目分组，例如，具有不同乐章的古典音乐。贝多芬第九交响曲最后一乐章的 MP3 文件可能为**内容组**指定为“D 大调第 9 号交响曲”，而**标题**为“Presto-O Freunde, nicht diese Tone-Allegro assai”。
- **版权**: 音乐的版权消息。
- **封面艺术**: 此字段让您[添加和编辑专辑封面艺术] (/Manual/file_operations/editing_metadata/music_properties/adding_cover_art.zh.md)——代表音乐的“封面艺术”（CD 封面等）的图片。
- **磁带编号**: 对于多磁带组，此字段让您指定此音乐出现的磁带编号。
- **编码人员**: 此字段通常用于编码曲目的人的姓名，或用于编码曲目的软件应用程序的名称。
- **流派**: 音乐的流派。您可以从多种常见流派的列表中选择，或自己输入。
- **初始键**: 用于指示曲目的初始音调，例如 **G#m**。
- **情绪**: 用此指定音乐的情绪（例如“背景音乐”、“派对”等）。
- **原版艺术家**: 曲目的原版艺术家。这可用于指定由其它人录制的翻唱版本中的原版艺术家或多位原版艺术家的姓名。若要指定多个艺术家，请用分号分隔。
- **出版商**: 音乐的出版商。
- **发行日期**: 音乐最初发行的日期。
- **副标题**: **副标题** 描述用于提供与**标题** 相关的其它信息，例如，如果标题为“Another Brick in the Wall, Part 2”，副标题可能是“Live in Berlin”。
- **标题**: 音乐的标题。
- **曲目编号**: 音乐的曲目编号，如果是多曲目作品（例如专辑）的一部分。您可以只指定曲目编号，也可以指定曲目总数（例如，曲目编号可以是**5**，也可以是**5 / 15**）。

  此字段中的**增量**选项让您在选择多个文件时自动分配递增的曲目编号。您输入的曲目编号将分配给第一个选定的文件，并且该编号将针对每个附加文件递增一次。您还可以指定您希望曲目编号在前导零中填充，方法是在**曲目编号**字段中输入前导零。

- **年份**: 音乐最初发行的年份。

更多内容：[添加封面艺术](/Manual/file_operations/editing_metadata/music_properties/adding_cover_art.zh.md)