# Default Material Map Properties

The default material map uses a physically based rendering (PBR) model. If
you've already worked with PBR materials before, you likely already have enough
knowledge to work with the default material. If not, there's also a lot of
resources available online about this.

But with that out of the way. Here's a brief overview of how the default
material map properties work in the context of Renda.

## Albedo

Albedo controls the main color of your object. It essentially determines how
much light is reflected by the material. The Albedo Adjust property functions as
a multiplier to the texture that you provided.

When no Albedo Texture is specified, a completely white texture is used. This
allows you to set the exact color using the Albedo Adjust property.

## Metallic

Metallic controls how much your material looks like a metal. A value of 0
indicates that the material is not a metal at all, such as plastic, wood, or
stone. And a value of 1 indicates that the material is completely metallic such
as steel, iron, or gold.

It is also possible to set this value to something in between 0 and 1. In the
real world particles are usually either metallic or nonmetallic, but if the
particles of a material are small enough it may look like they have a value in
between.

The Metallic Adjust property also functions as a multiplier on top of the
metallic texture. While it is possible to adjust the looks of your metallic
texture, this property is mostly intended for when no texture has been provided.

## Roughness

Roughness controls how smooth the surface of the material is. A rough surface
means more of the light rays that come in are bounced in a different direction.
Whereas a more smooth surface could make the material almost look like a mirror.

## Metallic Roughness Texture

A single texture and sampler is used to control the metallic and roughness.
Renda follows the glTF spec and uses the blue channel for metallic value, and
the green channel for the roughness value.

## Normal

A normal texture allows you to adjust in which direction the surface is
pointing, without the need to add extra geometry to your mesh. This can be a
very effective way to achieve a high level of detail while staying performant.

The 'Normal Scale' property adjusts how much of an effect the normal texture
has. When no normal texture is provided this property does nothing.
