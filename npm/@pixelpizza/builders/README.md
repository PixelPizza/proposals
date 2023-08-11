## @pixelpizza/builders

### Dependencies

- [@pixelpizza/assert](https://npmjs.com/package/@pixelpizza/assert) - Assertions of builder attributes

### File Structure

```ps
src/
  lib/
    component/
      button/
        ButtonBuilder.ts
      selectMenu/
        ChannelSelectMenuBuilder.ts
        MentionableSelectMenuBuilder.ts
        RoleSelectMenuBuilder.ts
        SelectMenuBuilder.ts
        StringSelectMenuBuilder.ts
        StringSelectMenuOptionBuilder.ts
        UserSelectMenuBuilder.ts
      textInput/
        TextInputBuilder.ts
      ActionRowBuilder.ts
      ComponentBuilder.ts
    embed/
      EmbedBuilder.ts
    interaction/
      command/
        chatInput/
          option/
            SlashCommandAttachmentOptionBuilder.ts
            SlashCommandBooleanOptionBuilder.ts
            SlashCommandChannelOptionBuilder.ts
            SlashCommandIntegerOptionBuilder.ts
            SlashCommandMentionableOptionBuilder.ts
            SlashCommandNumberOptionBuilder.ts
            SlashCommandRoleOptionBuilder.ts
            SlashCommandStringOptionBuilder.ts
            SlashCommandUserOptionBuilder.ts
          SlashCommandBuilder.ts
          SlashCommandSubcommandBuilder.ts
          SlashCommandSubcommandGroupBuilder.ts
        contextMenu/
          ContextMenuCommandBuilder.ts
      modal/
        ModalBuilder.ts
  index.ts
```

### Examples

#### EmbedBuilder

```typescript
class EmbedBuilder implements Builder<APIEmbed> {
  @Type("string")
  readonly #title?: string;

  // ...other properties

  public setTitle(title: string): this {
    this.#title = title;
    return this;
  }

  // ...other setters

  public build(): APIEmbed {
    return {
      title: this.#title,
      // ...other properties
    };
  }
}
```
