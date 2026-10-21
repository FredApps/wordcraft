# Floating rectangles inside fitted textboxes

For direct floating, unlinked autoFit textboxes with horizontal, top-aligned text, direct non-text rectangles using Front, Behind or Square wrapping do not paint or enlarge the fitted frame through their own bounds. Square wrapping still displaces text before fitting. Source objects, anchor characters and hit metadata remain available for editing and saving.

The rule matches source story, paragraph path and byte offset. Both shape paint and hit metadata must identify the eligible source rectangle. Equal rectangles do not establish ownership. Paragraph markers must match the object count.

The bounded class excludes inline parents, linked or turned boxes, center/bottom alignment, groups, nested textbox content, table-contained children, other shape kinds, outlined/effected/turned children and other wrapping modes. Children use column/paragraph anchoring without alignment overrides. Existing behavior remains for those inputs. No saved-frame fallback, shared alignment extent, measurement budget, counter rollback or cache policy changes.

Six original private native controls cover Plain, Front/Behind inside/crossing rectangles and Square wrapping. Plain and Front/Behind frames measure 17 pt; Square measures 57 pt after text displacement. The qualified matched-reader comparison retains these frame and paint distinctions. Eligible rectangles do not paint, including those inside the parent frame.

The published #2453 reader is identical on both fitting bases. TallInline retains its inline image, source owner, hit metadata and line ownership. Parent and candidate both measure 104.380859 pt, versus 103.1 pt in the native export. The inherited height delta is +1.280857 pt; the image origin is -0.5 pt on each axis, with unchanged image dimensions. This does not establish exact native TallInline geometry or raster parity. The six native cases establish only the bounded fitting and own-paint policy above.
