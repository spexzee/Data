# Data

jsx```
import { ListItem, Typography, Box } from '@mui/material';
import CircleRounded from '@mui/icons-material/CircleRounded';

interface PackageGuideline {
  title: string;
  description?: string;
}

const GuidelineList = ({ guideline, idx }: { guideline: PackageGuideline; idx: number }) => {
  return (
    <ListItem
      key={`${guideline?.title}-${idx}`}
      sx={{
        display: 'flex',
        alignItems: 'flex-start',
        pt: 0,
        pb: 1,
        gap: 1,
        '& .MuiTypography-root': {
          padding: 0,
          margin: 0
        }
      }}
    >
      <CircleRounded sx={{ 
        fontSize: 8, 
        color: '#000', 
        mt: '5px', 
        flexShrink: 0 
      }} />
      
      <Box sx={{ display: 'flex', flexDirection: 'column' }}>
        {guideline.title.includes(' - ') ? (
          <>
            <Typography component="span" sx={{ 
              fontSize: 14,
              lineHeight: 1.4,
              '& b': {
                fontWeight: 'bold',
                textTransform: 'uppercase'
              }
            }}>
              <b>{guideline.title.split(' - ')[0]}</b> - {guideline.title.split(' - ')[1]}
            </Typography>
          </>
        ) : (
          <Typography sx={{ fontSize: 14, lineHeight: 1.4 }}>
            {guideline.title}
          </Typography>
        )}
        
        {guideline.description && (
          <Typography sx={{ 
            fontSize: 14, 
            pl: 2,  // Add padding to align with the title text
            lineHeight: 1.4,
            whiteSpace: 'normal'
          }}>
            {guideline.description}
          </Typography>
        )}
      </Box>
    </ListItem>
  );
};
```
